# Result Summary

The FLX prototype completed a full hardware acceptance run on **8 June 2026**.

The run tested the fabric as a deterministic compute system, not as a single fixed demo. It covered field workloads, particle workloads, recovery behavior, adaptive dispatch, lattice memory mapping, reporting, plotting, and reference-model comparison.

## Summary Table

| Test Area | What Was Tested | Result |
|---|---|---:|
| Startup and health | hardware boot, SPI links, status reporting | Pass |
| Board deployment | 100T timing/MCS, Cmod MCS, config-memory verify | Pass |
| Field workloads | configurable 1D, 2D, and 3D field cases | Pass |
| Capacity checks | active logical fields up to 1024 points | Pass |
| Invalid input checks | rejected invalid workload configurations | Pass |
| Particle regression | 10,000,000-particle 3D run, 438 steps | Pass |
| Reference-model comparison | hardware result vs fixed-point reference-model result | Pass |
| Restore proof | controlled WAL restore path vs baseline and reference model | Pass |
| Wave demo | 2D wave-style propagation with restore | Pass |
| Adaptive dispatch | field, SHA-style, robotics-style, generic workload classes | Pass |
| CPU-style benchmark comparison | generic VM sum, SHA-256 nonce scan, robot/world-grid update | Pass |
| Flash-booted programmable adaptability | VM load, integer bitwork, Q16, reductions, lattice addressing, world-state cases | Pass |
| Lattice memory mapping | row, snake, and Morton layout checks | Pass |
| Route mailbox | local route read/status on live board | Pass |
| RTL simulation | hardware kernel simulation proof | Pass |
| Evidence generation | reports, plots, summaries, logs, hashes | Pass |

## Headline Result

The 10,000,000-particle 3D regression:

| Metric | Result |
|---|---:|
| Particles | 10,000,000 |
| Steps | 438 |
| Field type | 3D, 8 x 8 x 8 |
| Reference-model comparison | Pass |
| Final field mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Normalized overlap | 1.0 |
| Hardware mirror verification | Pass |

## Field Workload Result

| Case | Shape | Timesteps | A7 Cycles | Mismatches | Max Delta | Result |
|---|---:|---:|---:|---:|---:|---:|
| MTS 1D | 100 x 1 x 1 | 140 | 355006 | 0 | 0 | Pass |
| MTS 2D | 16 x 16 x 1 | 140 | 1094658 | 0 | 0 | Pass |
| MTS 3D | 8 x 8 x 8 | 140 | 2600730 | 0 | 0 | Pass |
| MTS 1D cap | 1024 x 1 x 1 | 2 | 52480 | 0 | 0 | Pass |
| MTS 2D cap | 32 x 32 x 1 | 2 | 64770 | 0 | 0 | Pass |
| MTS 3D cap | 10 x 10 x 10 | 2 | 75286 | 0 | 0 | Pass |

## Lattice Memory Result

| Check | Coverage | Result |
|---|---:|---:|
| Host exhaustive layout/round-trip/neighbour checks | 48 / 48 | Pass |
| Live COM5 board layout-map checks | 51 / 51 | Pass |
| Layout modes | row, snake, Morton | Pass |
| Active logical point cap | 1024 | Pass |
| Route status/read local board path | exercised | Pass |

The visual layout proof is [MEDIA/evidence_panels/lattice_memory_layout_panel.png](MEDIA/evidence_panels/lattice_memory_layout_panel.png).

## CPU-vs-FLX Benchmark Result

| Case | CPU Reference Rate | FLX Kernel Rate | FLX/CPU Kernel Ratio | Exact Match |
|---|---:|---:|---:|---:|
| Generic VM integer sum | 245398.767 words/s | 14814814.815 words/s | 60.370x | Pass |
| SHA-256 nonce scan | 140819.407 hashes/s | 829470.504 hashes/s | 5.890x | Pass |
| Robot/world-grid update | 3883200.597 cell-steps/s | 16407626.983 cell-steps/s | 4.225x | Pass |

The benchmark separates raw A7 kernel-cycle throughput from serial operator wall time. Source evidence is [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json), and the visual panel is [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png).

## Flash-Booted Adaptability Result

This run was executed after rebuilding the current A7 RTL, programming the generated `config_100t.mcs` into A7-100T configuration flash, booting from programmed configuration memory, and running the COM5 hardware tests. It adds workload diversity beyond the existing SHA/MTS/Particle3D/WAL cases.

| Case | Type | Expected | FLX Result | Result |
|---|---|---:|---:|---:|
| `vm_load_xor_bitwork` | integer bitwork | `0xB791F3DD` | `0xB791F3DD` | Pass |
| `vm_q16_multiply_load` | Q16 fixed-point arithmetic | `0xFFFFA000` | `0xFFFFA000` | Pass |
| `vm_rotr_bit_permutation` | bit permutation | `0x78123456` | `0x78123456` | Pass |
| `vm_filter_count_reduce` | filter/database count | `0x00000004` | `0x00000004` | Pass |
| `vm_checksum_xor_reduce` | checksum reduction | `0x6633423D` | `0x6633423D` | Pass |
| `vm_signed_min_reduce` | signed scan | `0xFFFFFFEC` | `0xFFFFFFEC` | Pass |
| `vm_signed_max_reduce` | signed scan | `0x00000005` | `0x00000005` | Pass |
| `vm_lattice_neighbor_index` | lattice addressing | `0x0000000B` | `0x0000000B` | Pass |
| `sand_fall_local_rules` | world-state local rules | `0x0534C9FA` | `0x0534C9FA` | Pass |
| `factory_conveyor_jam` | world-state local rules | `0x5C4FA6A5` | `0x5C4FA6A5` | Pass |
| `swarm_wrap_edges` | world-state local rules | `0x894C99C6` | `0x894C99C6` | Pass |

Source evidence is [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json), and the visual panel is [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png).

## Recovery Result

| Comparison | Result | Mismatches | Max Delta | Normalized Overlap |
|---|---:|---:|---:|---:|
| Checkpoint restore | Pass | 0 | 0 | 1.0 |
| Final restored run vs baseline | Pass | 0 | 0 | 1.0 |

## Source Evidence

- [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json)
- [evidence/board_deployment_20260608/README.md](evidence/board_deployment_20260608/README.md)
- [evidence/lattice_memory_20260608/lattice_memory_summary.json](evidence/lattice_memory_20260608/lattice_memory_summary.json)
- [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json)
- [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json)
