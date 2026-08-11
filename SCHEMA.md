# Repository conventions

Schema notes version: `cognityx-experiment-results/v1`.

Immutable snapshots use:

```text
experiments/<experiment-id>/<snapshot-id>/
  snapshot-manifest.json
  research-spec.yaml
  execution-plan.json
  experiment.json
  lineage.json
  statistics.json
  finding.json
  finding.md
  tables/
  figure-data/
```

The snapshot ID is the SHA-256 digest of the canonical snapshot manifest before
the ID is attached. A correction creates a new snapshot with
`supersedes_snapshot_id`; old directories are never changed or force-pushed.

Cumulative derived material uses:

```text
research/<research-area>/<hypothesis-id>/
  hypothesis.yaml
  evidence-ledger.jsonl
  evidence-summary.md
  <research-question-id>/
    rq.yaml
    findings.jsonl
    findings.md
    experiment-table.csv
    figure-data/
    experiments/<experiment-id>/snapshots.jsonl
```

Immutable finding and evidence-ledger rows are append-only. Markdown summaries
and aggregate tables are derived views and may be regenerated from those rows.
Storage URIs and checksums point back to authoritative evidence.
