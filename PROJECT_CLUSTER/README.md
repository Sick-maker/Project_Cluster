# Project Cluster

A **Notion-first + GitHub-backed** workspace for tracking the ongoing attempt to solve Kryptos **K4**.

- **Dense files** (configs, results, reports, briefings) live here in GitHub.
- **Notion** mirrors the state with databases and embeds for easy reading.
- Everything is reproducible: each run has a config, a manifest, and results.

## Core ideas
- **Single source of truth**: `/PROJECT_CLUSTER/data` (ciphertexts, anchors).
- **Every run is logged**: `/PROJECT_CLUSTER/runs/registry.csv` and `/PROJECT_CLUSTER/results/<RUN_ID>`.
- **Briefings after rounds**: `/PROJECT_CLUSTER/docs/briefings/` (post-experiment syntheses).
- **Methods are modular**: `/PROJECT_CLUSTER/methods/` (one folder per approach).
- **Schemas for consistency**: `/PROJECT_CLUSTER/tools/schemas` for config/result/briefing shapes.

> Indices are **1-based** for anchor windows. Keep this explicit in all code and docs.

## Day-to-day
1) Make a config in `configs/`.
2) Initialize a run (CLI or manually) → this creates `results/<RUN_ID>/` + `manifest.json`.
3) Execute the experiment with your harness; drop artifacts into the run folder.
4) Finalize: update `runs/registry.csv`, write a 1-pager in `docs/reports/`.
5) Commit & push. Paste/Embed GitHub links in Notion.
6) After a batch of runs, write a **briefing** in `docs/briefings/`.

## Minimal Notion setup
Create 3 databases in Notion (tables):
- **Runs**: Run ID, Date, Method, Config Path, Anchors Pass, Best Score, Artifacts Link, Notes.
- **Methods**: Method Name, Status, Summary, Docs Path/Link, Related Runs (Relation → Runs).
- **Briefings**: Briefing ID, Date, Title, TL;DR, Files Link, Related Runs (Relation → Runs).

Then embed these GitHub folders on your Notion hub page:
- `PROJECT_CLUSTER/data/`
- `PROJECT_CLUSTER/configs/`
- `PROJECT_CLUSTER/docs/reports/`
- `PROJECT_CLUSTER/docs/briefings/`
- `PROJECT_CLUSTER/results/`
