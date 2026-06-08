# Validation Card

## FLX1.0 (Finite Lattice maXimus)

Validation date: **8 June 2026**

Validation type: **hardware acceptance run with board deployment proof, reference-model comparison, controlled recovery, and lattice-memory mapping checks**

Final status: **PASS**

## Tested Capabilities

| Capability | Result |
|---|---:|
| 100T timing/MCS/programming gate | Pass |
| Cmod MCS/programming gate | Pass |
| Live board SPI health | Pass |
| 1D field-state workload | Pass |
| 2D field-state workload | Pass |
| 3D field-state workload | Pass |
| 1024-active-point field checks | Pass |
| 10,000,000-particle 3D regression | Pass |
| 438-step deterministic particle run | Pass |
| Controlled WAL restore/recovery proof | Pass |
| Wave propagation restore demo | Pass |
| Adaptive dispatch proof | Pass |
| Lattice memory mapper: row/snake/Morton | Pass |
| Live board route mailbox read/status | Pass |
| Invalid-configuration rejection | Pass |
| Hardware health checks | Pass |
| Evidence/report generation | Pass |

## Core Metrics

| Metric | Result |
|---|---:|
| Reference-model comparison | Pass |
| Final fixed-point mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Particle regression normalized overlap | 1.0 |
| Restore comparison normalized overlap | 1.0 |
| Lattice host mapping checks | 48 / 48 |
| Lattice live board checks | 51 / 51 |
| Documentation/help audit missing entries | 0 |

## Supported Claim

The FLX prototype has demonstrated deterministic hardware execution for field/world-state workloads, exact reference-model comparison for the validated cases, controlled restore behavior, deterministic 1D/2D/3D lattice memory mapping, and evidence generation.

## Scope

This validation card summarizes the measured prototype result and the acceptance evidence generated from that run.
