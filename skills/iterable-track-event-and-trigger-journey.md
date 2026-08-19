---
name: Track a user event and trigger a journey
description: >-
  Identify or update an Iterable user, track a behavioural event against them, then trigger a journey
  (workflow) that acts on it. This is the core Iterable ingestion-to-activation loop.
api: openapi/_original/iterable-api-openapi.json
operations:
  - updateUser
  - track
  - trackBulk
  - triggerWorkflow
  - User events
generated: '2026-08-13'
method: generated
source: >-
  Grounded in openapi/_original/iterable-api-openapi.json (harvested from https://api.iterable.com/api-docs
  2026-08-13); conventions from conventions/iterable-conventions.yml and errors/iterable-error-codes.yml.
---

# Track a user event and trigger a journey

## Before you call anything

- **Base URL depends on the project's data center.** USDC projects use `https://api.iterable.com`,
  EDC projects use `https://api.eu.iterable.com`. Every path is prefixed `/api`. A key created in one
  data center will fail against the other.
- **Auth:** send the project API key in the `Api-Key` header. Use a server-side key for these calls.
  Client-side keys should carry a JWT (see `authentication/iterable-authentication.yml`).
- **There is no idempotency key.** Retrying a failed write can duplicate events. Decide up front how
  you de-duplicate, and never split the same event stream across the bulk and non-bulk endpoints —
  Iterable only preserves ordering within one endpoint.

## Steps

1. **Upsert the user.**
   `POST /api/users/update` (operationId `updateUser`). Send `email` or `userId` plus `dataFields`.
   Iterable creates the profile if it does not exist. Watch for `InvalidEmailAddressError`,
   `InvalidUserIdError` and `RequestFieldsTypesMismatched` in the response `code`.

2. **Track the event.**
   `POST /api/events/track` (operationId `track`) with `email`/`userId`, `eventName`, optional
   `dataFields` and `createdAt`. For volume, use `POST /api/events/trackBulk` (operationId
   `trackBulk`) — up to 1,000 events per request. Both are asynchronous; a 200 means accepted for
   processing, not applied.

3. **Confirm ingestion (optional, read).**
   `GET /api/events/{email}` (operationId `User events`) or `GET /api/events/byUserId/{userId}`
   (operationId `User events by userId`). Both return PII — treat as sensitive.

4. **Trigger the journey.**
   `POST /api/workflows/triggerWorkflow` (operationId `triggerWorkflow`) with the `workflowId` and
   the recipient. List available journeys first with `GET /api/journeys` (operationId `getJourneys`).

## Rules

- Do not create new custom event definitions from client-side keys unless the project's "Allow event
  track calls" window is open — otherwise unknown event names are silently ignored.
- Avoid concurrent updates to the same user and concurrent creation of new fields; Iterable
  documents both as race conditions.
- On `429 RateLimitExceeded`, back off exponentially. Per-endpoint limits are in
  `rate-limits/iterable-rate-limits.yml`; `POST /api/events/track` limits are counted **per project**,
  so your integration shares them with Smart Ingest and every other consumer.
