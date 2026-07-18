# GPT-5.6 Luna Trajectories — 2026-07-18

Benchmark repository:

- `Liu-Ruotian/agentdojo-benchmark`

Trajectory groups:

## Codex 1

Root:

- `runs/2026-07-18/codex1/`

Domains:

- airport
- automotive
- employment
- logistics
- telecom
- ticketing

Manifest:

- `codex1_manifest.txt`

## Codex 2

Root:

- `runs/2026-07-18/codex2/`

Domains:

- banking
- ecommerce
- government
- healthcare
- saas
- university

Manifest:

- `codex2_manifest.txt`

## Review scope

For each GPT-5.6 Luna trajectory, review only:

1. Whether the automatic utility judgment is wrong.
2. Whether the benchmark task has a major design flaw.

Ignore minor trajectory-quality issues and the deprecated `poison_top1`
condition itself.

Current evaluator path:

- `suites/<domain>/tasks/<domain>_tXX/eval.yaml`
