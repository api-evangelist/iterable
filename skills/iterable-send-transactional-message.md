---
name: Send a transactional message from a template
description: >-
  Find or update a template, send it to one user over email, SMS, push, web push, in-app or WhatsApp,
  and cancel a scheduled send if needed.
api: openapi/_original/iterable-api-openapi.json
operations:
  - getTemplates
  - getEmailTemplate
  - previewEmailTemplate
  - emailProof
  - target
  - cancel
generated: '2026-08-13'
method: generated
source: >-
  Grounded in openapi/_original/iterable-api-openapi.json (harvested from https://api.iterable.com/api-docs
  2026-08-13). Channel target/cancel operations all carry the operationIds `target` and `cancel`,
  distinguished by path — always reference the path, not the id alone.
---

# Send a transactional message from a template

## Pick the template

- `GET /api/templates` (operationId `getTemplates`) lists templates; filter by `templateType` and
  `messageMedium`.
- `GET /api/templates/email/get` (operationId `getEmailTemplate`) returns one email template; the
  siblings are `/api/templates/push/get`, `/api/templates/sms/get`, `/api/templates/inapp/get`
  (operationIds `getPushTemplate`, `getSMSTemplate`, `getInAppTemplate`).
- `GET /api/templates/getByClientTemplateId` (operationId `getByClientTemplateId`) resolves your own
  identifier to an Iterable template.

## Verify before you send

- `POST /api/templates/email/preview` (operationId `previewEmailTemplate`) renders the template with
  supplied user/event/data-feed data and returns the HTML — no message is sent.
- `POST /api/templates/email/proof` (operationId `emailProof`) sends a proof to a named recipient.
  Siblings: `/api/templates/inapp/proof`, `/api/templates/push/proof`, `/api/templates/sms/proof`.

## Send

Each channel has its own send path, and every one of them uses the operationId `target`:

| Channel | Operation |
|---|---|
| Email | `POST /api/email/target` |
| SMS | `POST /api/sms/target` |
| Push | `POST /api/push/target` |
| Web push | `POST /api/webPush/target` |
| In-app | `POST /api/inApp/target` |
| WhatsApp | `POST /api/whatsApp/target` |

Send `campaignId` plus the recipient (`recipientEmail` or `recipientUserId`) and any
`dataFields`/`metadata` the template expects.

## Cancel

`POST /api/email/cancel`, `/api/sms/cancel`, `/api/push/cancel`, `/api/webPush/cancel`,
`/api/inApp/cancel`, `/api/whatsApp/cancel` (all operationId `cancel`) cancel a scheduled send for a
specific user.

## Rules

- The send is real. There is no test mode and no test-key prefix — use a project dedicated to
  development, as Iterable's own getting-started guide instructs.
- Errors come back as `{msg, code, params}`, not problem+json. `QueueEmailError` at 400 is your
  fault; at 500 it is Iterable's. See `errors/iterable-error-codes.yml`.
- Check `GET /api/channels` (operationId `channels`) and `GET /api/messageTypes` (operationId
  `messageTypes`) when a send is rejected for channel or subscription reasons.
