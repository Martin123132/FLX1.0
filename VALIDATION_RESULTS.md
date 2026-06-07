# Validation Results

## Latest Validated Run

Date: **6 June 2026**

Final result: **PASS**

The prototype was tested through a full hardware acceptance flow. The result was compared against CPU-reference outputs for the validated workloads.

The generated reports, logs, plots, summaries, and file-integrity hashes are stored in [evidence/acceptance_20260606_full](evidence/acceptance_20260606_full/).

## Field Workloads

| Workload | Public Scale | Comparison Result | Mismatches | Max Delta |
|---|---:|---:|---:|---:|
| 1D field | 100 active points | Pass | 0 | 0 |
| 2D field | 16 x 16 active field | Pass | 0 | 0 |
| 3D field | 8 x 8 x 8 active field | Pass | 0 | 0 |
| 1D cap check | 1024 active points | Pass | 0 | 0 |
| 2D cap check | 32 x 32 active field | Pass | 0 | 0 |
| 3D cap check | 10 x 10 x 10 active field | Pass | 0 | 0 |

## Particle Regression

| Metric | Result |
|---|---:|
| Particle count | 10,000,000 |
| Steps | 438 |
| Field type | 3D |
| CPU-reference comparison | Pass |
| Final field mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Normalized overlap | 1.0 |

## Restore / Recovery

| Comparison | Result | Mismatches | Max Delta | Normalized Overlap |
|---|---:|---:|---:|---:|
| CPU reference vs hardware baseline | Pass | 0 | 0 | 1.0 |
| CPU reference vs restored hardware run | Pass | 0 | 0 | 1.0 |
| Hardware baseline vs restored hardware run | Pass | 0 | 0 | 1.0 |

## Adaptive Dispatch

| Workload Class | Selected Path | Result |
|---|---|---:|
| SHA-style deterministic workload | accelerator-capable path | Pass |
| Robotics/world-grid style workload | accelerator-capable path | Pass |
| Wave/field workload | field-physics path | Pass |
| Generic programmable workload | programmable fallback path | Pass |

## Overall Statement

The validated prototype demonstrated deterministic field-state workload execution, exact CPU-reference agreement for the tested cases, controlled restore behavior, adaptive workload dispatch, and evidence/report generation.
