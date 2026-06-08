# Validation Results

## Latest Validated Run

Date: **8 June 2026**

Final result: **PASS**

The prototype was tested through a full hardware acceptance flow. The run included board deployment evidence, live board health checks, reference-model comparisons, controlled WAL recovery, and lattice-memory mapping checks.

## Board Deployment Gates

| Gate | Evidence | Result |
|---|---|---:|
| 100T routed timing | `ROUTED_WNS=0.134` | Pass |
| 100T MCS generated | `config_100t.mcs` | Pass |
| 100T config-memory verify | `Program/Verify Operation successful`, Done HIGH | Pass |
| Cmod config-memory verify | `Program/Verify Operation successful`, Done HIGH | Pass |
| Live board health | `SPI1 (A7): OK`, `SPI0 (Cmod): OK` | Pass |
| Cmod mirror check | all 512 raw mirrored sites matched A7 | Pass |

Source: [evidence/board_deployment_20260608](evidence/board_deployment_20260608/README.md)

## Field Workloads

| Workload | Validated Scale | Timesteps | A7 Cycles | Mismatches | Max Delta | Result |
|---|---:|---:|---:|---:|---:|---:|
| 1D field | 100 active points | 140 | 355006 | 0 | 0 | Pass |
| 2D field | 16 x 16 active field | 140 | 1094658 | 0 | 0 | Pass |
| 3D field | 8 x 8 x 8 active field | 140 | 2600730 | 0 | 0 | Pass |
| 1D cap check | 1024 active points | 2 | 52480 | 0 | 0 | Pass |
| 2D cap check | 32 x 32 active field | 2 | 64770 | 0 | 0 | Pass |
| 3D cap check | 10 x 10 x 10 active field | 2 | 75286 | 0 | 0 | Pass |

Source: [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json)

## Lattice Memory Mapping

| Check | Coverage | Result |
|---|---:|---:|
| Host layout, round-trip, neighbour checks | 48 / 48 | Pass |
| Live board layout-map cross-checks | 51 / 51 | Pass |
| 1D logical memory | up to 1024 points | Pass |
| 2D logical memory | up to 32 x 32 | Pass |
| 3D logical memory | 8 x 8 x 8 and 10 x 10 x 10 | Pass |
| Layout modes | row, snake, Morton | Pass |
| Route local read/status | exercised on live board | Pass |

Visual evidence:

- [MEDIA/evidence_panels/lattice_memory_layout_panel.png](MEDIA/evidence_panels/lattice_memory_layout_panel.png)
- [MEDIA/plots/lattice_layout_2d_32x32_row_snake_morton.png](MEDIA/plots/lattice_layout_2d_32x32_row_snake_morton.png)
- [MEDIA/plots/lattice_layout_3d_8x8x8_row_snake_morton.png](MEDIA/plots/lattice_layout_3d_8x8x8_row_snake_morton.png)
- [MEDIA/plots/lattice_layout_3d_10x10x10_row_snake_morton.png](MEDIA/plots/lattice_layout_3d_10x10x10_row_snake_morton.png)

Source: [evidence/lattice_memory_20260608/lattice_memory_summary.json](evidence/lattice_memory_20260608/lattice_memory_summary.json)

## CPU-vs-FLX Benchmark Comparison

This live COM5 benchmark compares CPU-reference implementations against FLX hardware paths. FLX kernel rate is calculated from A7 cycle counters and excludes UART command/load/readback overhead. FLX wall rate is retained in the JSON/CSV evidence for operator-run cost.

| Case | What It Tests | CPU Reference Rate | FLX Kernel Rate | FLX/CPU Kernel Ratio | Exact Match |
|---|---|---:|---:|---:|---:|
| Generic VM integer sum | programmable CPU-style integer reduction | 245398.767 words/s | 14814814.815 words/s | 60.370x | Pass |
| SHA-256 nonce scan | deterministic integer/hash workload | 140819.407 hashes/s | 829470.504 hashes/s | 5.890x | Pass |
| Robot/world-grid update | branching local-state workload | 3883200.597 cell-steps/s | 16407626.983 cell-steps/s | 4.225x | Pass |

Visual evidence:

- [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png)

Source: [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json)

## Flash-Booted Programmable Adaptability Suite

This live COM5 run was executed after rebuilding the A7-100T design from the current RTL source. The new bitstream passed routed timing with `WNS=0.239 ns`, `TNS=0`; `config_100t.mcs` was generated, programmed into configuration flash, verified, booted from programmed configuration memory, and then tested live.

| Case | What It Tests | CPU Expected | FLX Result | Kernel Ratio | Result |
|---|---|---:|---:|---:|---:|
| `vm_load_xor_bitwork` | RAM LOAD + XOR + STORE | `0xB791F3DD` | `0xB791F3DD` | `3.529x` | Pass |
| `vm_q16_multiply_load` | RAM LOAD + Q16 multiply + STORE | `0xFFFFA000` | `0xFFFFA000` | `2.432x` | Pass |
| `vm_rotr_bit_permutation` | RAM LOAD + rotate-right bit permutation | `0x78123456` | `0x78123456` | `2.727x` | Pass |
| `vm_filter_count_reduce` | database/filter-style count reduction | `0x00000004` | `0x00000004` | `1.765x` | Pass |
| `vm_checksum_xor_reduce` | checksum/integer reduction | `0x6633423D` | `0x6633423D` | `4.615x` | Pass |
| `vm_signed_min_reduce` | signed minimum scan | `0xFFFFFFEC` | `0xFFFFFFEC` | `1.923x` | Pass |
| `vm_signed_max_reduce` | signed maximum scan | `0x00000005` | `0x00000005` | `2.308x` | Pass |
| `vm_lattice_neighbor_index` | lattice-neighbour index helper | `0x0000000B` | `0x0000000B` | `2.500x` | Pass |
| `sand_fall_local_rules` | world-state local movement rules | `0x0534C9FA` | `0x0534C9FA` | `6.610x` | Pass |
| `factory_conveyor_jam` | factory/conveyor jam propagation | `0x5C4FA6A5` | `0x5C4FA6A5` | `3.904x` | Pass |
| `swarm_wrap_edges` | swarm/grid edge wrapping and collisions | `0x894C99C6` | `0x894C99C6` | `5.988x` | Pass |

Visual evidence:

- [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png)

Source: [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json)

## Particle Regression

| Metric | Result |
|---|---:|
| Particle count | 10,000,000 |
| Steps | 438 |
| Field type | 3D, 8 x 8 x 8 |
| Reference-model comparison | Pass |
| Final field mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Normalized overlap | 1.0 |
| Cmod mirror verified | True |

Source: [evidence/acceptance_20260608_full/particle3d_438/compare_final_cpu_vs_fpga/compare_report.json](evidence/acceptance_20260608_full/particle3d_438/compare_final_cpu_vs_fpga/compare_report.json)

## Restore / Recovery

| Comparison | Result | Mismatches | Max Delta | Normalized Overlap |
|---|---:|---:|---:|---:|
| Checkpoint restore | Pass | 0 | 0 | 1.0 |
| Final restored run vs baseline | Pass | 0 | 0 | 1.0 |
| Wave baseline vs restored | Pass | 0 | 0 | 1.0 |

Source: [evidence/acceptance_20260608_full/fault_recovery](evidence/acceptance_20260608_full/fault_recovery)

## Adaptive Dispatch

| Workload Class | Selected Path | Result |
|---|---|---:|
| SHA-style deterministic compute | accelerator-capable path | Pass |
| Robotics/world-grid style workload | accelerator-capable path | Pass |
| Wave/field workload | field-physics path | Pass |
| Generic programmable workload | programmable fallback path | Pass |

## Dense 3D Generality Cases

These prior cases are retained because they provide visually dense field examples.

| Workload | Validated Scale | Comparison Result | Mismatches | Max Delta | Overlap |
|---|---:|---:|---:|---:|---:|
| Delta-style 3D field | 8 x 8 x 8, 512 active points | Pass | 0 | 0 | 0.9999999999999998 |
| Gaussian-style 3D field | 8 x 8 x 8, 512 active points | Pass | 0 | 0 | 1.0 |
| Plane-wave-style 3D field | 8 x 8 x 8, 512 active points | Pass | 0 | 0 | 0.9999999999999999 |
| Seeded-random-style 3D field | 8 x 8 x 8, 512 active points | Pass | 0 | 0 | 1.0000000000000002 |

Source: [evidence/flx3d_generality_20260524/summary.json](evidence/flx3d_generality_20260524/summary.json)

## Overall Statement

The validated prototype demonstrated deterministic execution, exact reference-model agreement for the tested cases, controlled restore behavior, adaptive workload dispatch, layout-aware lattice memory mapping, live board route checks, and evidence generation.

For the experiment-by-experiment media/source mapping, see [EVIDENCE_CORRELATION.md](EVIDENCE_CORRELATION.md).
