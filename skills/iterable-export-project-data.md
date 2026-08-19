---
name: Export Iterable project data
description: >-
  Run an asynchronous Iterable data export job, poll it, and download the files — plus the synchronous
  CSV/JSON alternatives for smaller pulls.
api: openapi/_original/iterable-api-openapi.json
operations:
  - startExport
  - getExportJobs
  - getExportFiles
  - cancelExport
  - exportDataCsv
  - exportDataJson
  - exportUserEvents
generated: '2026-08-13'
method: generated
source: >-
  Grounded in openapi/_original/iterable-api-openapi.json (harvested from https://api.iterable.com/api-docs
  2026-08-13); rate limits read from the same document.
---

# Export Iterable project data

## Asynchronous export (preferred for volume)

1. **Start the job.** `POST /api/export/start` (operationId `startExport`) with the data types and
   date range. Rate limit: **1 request/second, per organization** — additive across every project and
   key in the org, and additional requests queue when the concurrent limit is reached.
2. **Poll.** `GET /api/export/{jobId}/files` (operationId `getExportFiles`) returns job status and
   download URLs as files become available; page with `startAfter`. Each file is up to 10MB and a job
   is capped at 100GB. A job can flip from `running` back to `enqueued` after a restart without
   losing progress.
3. **List jobs.** `GET /api/export/jobs` (operationId `getExportJobs`), filterable by state
   (`enqueued`, `queued`, `running`, `completed`, `failed`, `cancelled`, `cancelling`).
4. **Cancel.** `DELETE /api/export/{jobId}` (operationId `cancelExport`). Rate limit: 1 request/second,
   per project.

## Synchronous export (small pulls only)

- `GET /api/export/data.csv` (operationId `exportDataCsv`) and `GET /api/export/data.json`
  (operationId `exportDataJson`) — campaign analytics; require either `range` or
  `startDateTime`+`endDateTime`. Rate limit: **4 requests/minute, per project**.
- `GET /api/export/userEvents` (operationId `exportUserEvents`) — user event stream.

## Rules

- Exports return user PII. In the MCP server these tools sit behind the `ITERABLE_USER_PII` flag;
  apply the same care in your own integration.
- `data.json` returns one JSON entry per line, not a JSON array — stream it.
- A 202 means the export was accepted, not finished. Never treat the start call's response as data.
- Back off on `429 RateLimitExceeded`; the export limits are the tightest in the API.
