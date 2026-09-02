# job-watcher-data

Public data feed for the new grad job watcher. **Nothing here is written by hand.**

GitHub Actions in the (private) watcher repo runs a sweep every 5 minutes and
pushes the result here. The dashboard at <https://htarek.systems/jobs> fetches
these files directly, because `raw.githubusercontent.com` serves
`Access-Control-Allow-Origin: *` and a static page therefore has no backend to
call.

| file | contents |
|---|---|
| `jobs.json` | current open matching roles |
| `health.json` | per source last success, error, latency |

This repo exists so the watcher itself can stay private: the company slugs it
targets and its sweep history are not published, only the resulting job feed.

Application status (applied / skipped / interviewing) is **not** here. It lives
in the browser's localStorage, per device, and is never uploaded.
