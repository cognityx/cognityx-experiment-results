# Repository conventions

Schema notes version: `cognityx-experiment-results/v1`.

Every snapshot manifest records the declared publication policy and the
effective `public_summary` projection. A public preregistration uses:

```text
experiments/<experiment-id>/<snapshot-id>/
  snapshot-manifest.json
  preregistration.json
```

The preregistration keeps the hypothesis, research questions, treatment roles,
seeds, outcome and stopping rules, exact model/software revisions, and plan
checksums. It does not copy treatment inputs, source content, dataset paths,
credentials, or environment details.

A public terminal snapshot uses:

```text
experiments/<experiment-id>/<snapshot-id>/
  snapshot-manifest.json
  research-summary.json
  statistics.json
  resources-summary.json
  finding.json
  finding.md
  tables/
  figure-data/
  lineage-summary.json
```

The terminal view contains aggregate results and opaque identities, revisions,
and checksums. It never contains `records.jsonl`, raw prediction rows, source or
answer text, judge requests or responses, private Storage addresses, local
paths, credentials, model or adapter bytes, or full telemetry streams. If a
file cannot be shown to follow the public whitelist, it is not published.

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
The journal contains public-safe findings, checksums, snapshot paths, and opaque
execution identities; it does not expose private Storage addresses or
record-level evidence. Cognityx Storage remains the authority for the complete
evidence.
