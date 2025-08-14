# Conventions

## IDs
- Run ID: `PC-YYYYMMDD-HHMM-<CODE>`
- Briefing ID: `BRF-YYYYMMDD-<TAG>`
- Method code: short uppercase (e.g., `MKS`, `QGM`, `TPV`).

## Commits
- `run(init): <RUN_ID> ...`
- `run(finalize): <RUN_ID> score=<X> anchors=<pass|fail>`
- `briefing: <BRF_ID> <title>`

## Folders
- `/results/<RUN_ID>/` is append-only after finalize.
- Large tables as CSV; summaries as Markdown.
