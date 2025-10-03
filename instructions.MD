# DTCC Platform Roadmap — GitHub Integration (Short)

## Objective

Create a single, living roadmap that drives work across ~20 repos without losing issues or priorities.

## Source of Truth (Two Pieces)

1. **Org-level GitHub Project (v2)** — "DTCC Platform Roadmap"
2. **Meta-repo** (e.g., `dtcc-platform`) — holds the sprint outcomes and a canonical `features.yaml`

## GitHub Project Setup

### Fields

- **Stage**: Ingest & Manage / Prepare / Analyze & Simulate / Visualize / Deliver / Backbone / Engineering
- **Package**: `dtcc-core` / `dtcc-sim` / `dtcc-ue` / `dtcc-viewer` / `dtcc-solar` / `dtcc-tetgen` / other
- **Status**: Now / Next / Later / In Review / Done / Icebox
- **Priority**: P0 / P1 / P2 / P3
- **Owner**, **Iteration** (2-week), **Target Release** (e.g., 2025.Q4)

### Saved Views

- "This iteration"
- "P0/P1"
- "By Stage"
- "By Package"

## Meta-Repo Contents

- `roadmap/2025Q4-sprint-outcomes.md` — copy the feature tables (have/want)
- `roadmap/features.yaml` — registry with: `id`, `title`, `stage`, `package`, `status`, `priority`, `owner`, `depends_on`, `acceptance`
- `roadmap/roadmap.md` — short overview linking to the Project views

## Labels & Templates (Sync to All Repos)

### Labels

- `stage:ingest-manage` | `stage:prepare` | `stage:analyze-simulate` | `stage:visualize` | `stage:deliver`
- `area:backbone` | `area:engineering`
- `type:feature` | `type:bug` | `type:techdebt` | `type:docs`
- `priority:P0` | `priority:P1` | `priority:P2` | `priority:P3`
- `pkg:<package>`

### Issue Template (Feature)

Fields for Stage, Package, acceptance criteria, docs note.

## Automation (Minimal but Effective)

1. **Auto-add to Project**: When an issue has `type:feature` + any `stage:*`, add it to the org Project and map labels → fields (set Package from repo name by default)

2. **Staleness**: If not updated in 45 days and not `Status=Now`, move to Icebox and comment with a revive instruction

3. **Weekly digest**: Action in meta-repo posts a summary (new/closed/slipped P0/P1) to Slack/Teams and writes `reports/weekly.md`

4. **Docs gate**: PRs that close `type:feature` must touch `docs/examples` or carry `no-docs-required`

## Operating Cadence

- **Weekly** 30-min triage (view: "This iteration")
- **Bi-weekly** iteration planning
- **Monthly** roadmap review (top 10 items)
- **Quarterly** release train (ship what's Done; slip items move with a note)

## Immediate Next Steps

1. Create the org Project with fields + saved views
2. Create `dtcc-platform` meta-repo and add `features.yaml` + sprint outcomes
3. Roll out labels + feature template to all repos (script)
4. Add the three automations above
5. Seed the board from the sprint tables and start the first 2-week iteration
