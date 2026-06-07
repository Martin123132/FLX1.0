# Benchmarks

The benchmark evidence is used here as validation evidence, not as a throughput claim. The important result is repeatable agreement between the hardware path and the CPU/reference model for the validated cases.

## Acceptance Benchmark Summary

| Case | Workload Class | Public Scale | Result |
|---|---|---:|---:|
| Field 1D | deterministic field | 100 active points, extended run | Pass |
| Field 2D | deterministic field | 16 x 16 active field, extended run | Pass |
| Field 3D | deterministic field | 8 x 8 x 8 active field, extended run | Pass |
| Field 1D cap | deterministic field | 1024 active points | Pass |
| Field 2D cap | deterministic field | 32 x 32 active field | Pass |
| Field 3D cap | deterministic field | 10 x 10 x 10 active field | Pass |
| Particle3D regression | particle-to-field | 10,000,000 particles, 438 steps | Pass |
| Wave restore | field recovery | 2D wave-style restore demo | Pass |
| Recovery proof | state recovery | controlled restore path | Pass |
| Adaptive dispatch | workload routing | field, SHA-style, robotics-style, generic | Pass |

## Comparison Metrics

The benchmark suite reports:

- fixed-point mismatch count;
- maximum fixed-point delta;
- normalized overlap;
- CPU-reference comparison status;
- restore comparison status;
- pass/fail status for invalid configuration handling.

## Headline Numbers

| Metric | Result |
|---|---:|
| Full acceptance status | Pass |
| Particle3D workload size | 10,000,000 particles |
| Particle3D run length | 438 steps |
| Particle3D final mismatches | 0 |
| Particle3D maximum fixed-point delta | 0 |
| Particle3D normalized overlap | 1.0 |
| Restore proof mismatches | 0 |
| Restore proof maximum fixed-point delta | 0 |
| Restore proof normalized overlap | 1.0 |

## Interpretation

The useful benchmark result is not just throughput. The important property is that the prototype can run hardware workloads and show that the result matches the CPU-reference path exactly for the validated cases.

That matters for physical-world simulation, robotics, factory-state replay, digital twins, and fault-recoverable processing, where being able to replay and validate state can be as important as raw execution speed.

The generated benchmark artefacts are stored in [evidence/acceptance_20260606_full/benchmark_reports](evidence/acceptance_20260606_full/benchmark_reports).
