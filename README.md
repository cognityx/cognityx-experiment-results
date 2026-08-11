# Cognityx Experiment Results

This public repository holds compact, reviewer-friendly summaries produced by
Cognityx Experiments. In ordinary language, it is the public research-notebook
view: frozen questions and designs, revisions, checksums, aggregate statistics,
findings, tables, and figure-ready data. The complete scientific artifacts
remain in Cognityx Storage.

```text
Cognityx component publications in Storage
                    ↓ whitelisted snapshot
          cognityx-experiment-results
                    ↓
       human review and paper preparation
```

## Public-data warning

Everything committed here is public. Cognityx Experiments may publish here only
when the frozen policy selects `public_summary` and classifies the data as
`public`. Research classified `internal`, `confidential`, `restricted`, or left
unspecified must use a separately governed private results repository or no Git
publication at all.

Public-summary snapshots are built from a strict list of approved aggregate
fields. They intentionally omit individual evaluator or prediction records,
prompts, generated/candidate/reference answers, source passages and extracts,
raw training examples, private Storage addresses, secrets, credentials,
environment variables, personal or private source data, model weights,
adapters, checkpoints, raw PDFs, MLflow databases, full telemetry streams,
user-home paths, and temporary-directory paths.

Cognityx Storage remains the authoritative rich evidence location. A public Git
summary is useful for review and paper preparation, but it is not a replacement
for the access-controlled evidence and publication receipt in Storage.

This bootstrap contains no synthetic or real scientific result.

See [SCHEMA.md](SCHEMA.md) for immutable snapshot and journal conventions.
