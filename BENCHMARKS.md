# Benchmarks

## CPU-vs-FLX Hardware Benchmark

Source: [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json)

This live COM5 run compares normal CPU-style reference workloads against FLX hardware paths. The table separates **FLX kernel rate** from **FLX wall rate**. Kernel rate is calculated from A7 cycle counters and measures the fabric work. Wall rate includes UART command loading and readback, so it is useful for operator-run overhead but not raw fabric throughput.

| Case | What It Shows | CPU Reference Rate | FLX Kernel Rate | FLX/CPU Kernel Ratio | Exact Match |
|---|---|---:|---:|---:|---:|
| `vm_sum4` | generic programmable integer reduction | 245398.767 words/s | 14814814.815 words/s | 60.370x | Pass |
| `sha256_nonce_scan` | normal deterministic integer/hash workload | 140819.407 hashes/s | 829470.504 hashes/s | 5.890x | Pass |
| `robot_grid_world_state` | deterministic local-state/world-grid workload | 3883200.597 cell-steps/s | 16407626.983 cell-steps/s | 4.225x | Pass |

Media: [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png)

## Flash-Booted Adaptability Hardware Benchmark

Source: [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json)

This run adds programmable workload coverage beyond the existing SHA/MTS/Particle3D/WAL evidence. The A7-100T design was rebuilt from current RTL, routed timing passed with `WNS=0.239 ns`, `config_100t.mcs` was programmed and verified in config flash, the FPGA was booted from configuration memory, and the live COM5 run passed. Kernel ratios are calculated from A7 cycle counters and exclude UART command/load/readback overhead.

| Case | What It Shows | CPU Reference Rate | FLX Kernel Rate | FLX/CPU Kernel Ratio | Exact Match |
|---|---|---:|---:|---:|---:|
| `vm_load_xor_bitwork` | RAM load/store plus integer XOR | 1666669.134 ops/s | 5882352.941 ops/s | 3.529x | Pass |
| `vm_q16_multiply_load` | RAM load/store plus fixed-point Q16 multiply | 2222223.266 ops/s | 5405405.405 ops/s | 2.432x | Pass |
| `vm_rotr_bit_permutation` | integer rotate-right bit permutation | 1111111.633 ops/s | 3030303.030 ops/s | 2.727x | Pass |
| `vm_filter_count_reduce` | database/filter-style count reduction | 13333312.651 words/s | 23529411.765 words/s | 1.765x | Pass |
| `vm_checksum_xor_reduce` | checksum/integer XOR reduction | 3333338.268 words/s | 15384615.385 words/s | 4.615x | Pass |
| `vm_signed_min_reduce` | signed minimum scan | 7999997.292 words/s | 15384615.385 words/s | 1.923x | Pass |
| `vm_signed_max_reduce` | signed maximum scan | 6666696.747 words/s | 15384615.385 words/s | 2.308x | Pass |
| `vm_lattice_neighbor_index` | lattice-neighbour address helper | 91428825.576 ops/s | 228571428.571 ops/s | 2.500x | Pass |
| `sand_fall_local_rules` | local-rule world-state update | 2419659.726 cell-steps/s | 15993336.110 cell-steps/s | 6.610x | Pass |
| `factory_conveyor_jam` | factory/conveyor blocked-flow update | 4163955.738 cell-steps/s | 16256032.512 cell-steps/s | 3.904x | Pass |
| `swarm_wrap_edges` | wrapped-edge swarm/collision update | 2707403.041 cell-steps/s | 16211652.125 cell-steps/s | 5.988x | Pass |

Media: [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png)

## Latest Acceptance Benchmark Summary

Source: [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json)

| Case | Dimension | Shape | Points | Timesteps | A7 Cycles | Cycles / Point / Step | Mismatches | Max Delta | Result |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| `mts_1d_100_t140` | 1D | 100 x 1 x 1 | 100 | 140 | 355006 | 25.3576 | 0 | 0 | Pass |
| `mts_2d_16x16_t140` | 2D | 16 x 16 x 1 | 256 | 140 | 1094658 | 30.5429 | 0 | 0 | Pass |
| `mts_3d_8x8x8_t140` | 3D | 8 x 8 x 8 | 512 | 140 | 2600730 | 36.2825 | 0 | 0 | Pass |
| `mts_1d_1024_t2` | 1D cap | 1024 x 1 x 1 | 1024 | 2 | 52480 | 25.6250 | 0 | 0 | Pass |
| `mts_2d_32x32_t2` | 2D cap | 32 x 32 x 1 | 1024 | 2 | 64770 | 31.6260 | 0 | 0 | Pass |
| `mts_3d_10x10x10_t2` | 3D cap | 10 x 10 x 10 | 1000 | 2 | 75286 | 37.6430 | 0 | 0 | Pass |
| `wave_restore_2d` | 2D restore | 4 x 4 x 1 | 16 | 32 | 20514 | recorded in report | 0 | 0 | Pass |
| `particle3d_438_10m` | 3D particle | 8 x 8 x 8 | 512 | 438 | recorded in report | recorded in report | 0 | 0 | Pass |

## Board Deployment Benchmarks

| Gate | Measurement | Result |
|---|---:|---:|
| 100T routed WNS | 0.134 ns | Pass |
| 100T MCS program/verify | successful | Pass |
| Cmod MCS program/verify | successful | Pass |
| Done pin after 100T program | HIGH | Pass |
| Done pin after Cmod program | HIGH | Pass |

Source: [evidence/board_deployment_20260608](evidence/board_deployment_20260608/README.md)

## Lattice Memory Benchmarks

| Case | Coverage | Result |
|---|---:|---:|
| Host layout mapping cases | 48 / 48 | Pass |
| Live board layout-map cases | 51 / 51 | Pass |
| 1D 1024 mapping | row, snake, Morton | Pass |
| 2D 32 x 32 mapping | row, snake, Morton | Pass |
| 3D 8 x 8 x 8 mapping | row, snake, Morton | Pass |
| 3D 10 x 10 x 10 mapping | row, snake, Morton | Pass |
| Route local read/status | live board exercised | Pass |

Source: [evidence/lattice_memory_20260608/lattice_memory_summary.json](evidence/lattice_memory_20260608/lattice_memory_summary.json)

## Comparison Metrics Reported

The benchmark suite records:

- fixed-point mismatch count;
- maximum fixed-point delta;
- normalized overlap;
- density/field-norm metrics;
- reference-model comparison status;
- restore comparison status;
- invalid-configuration handling;
- board health and deployment status;
- file-integrity hashes.

## Interpretation

The useful benchmark result is not only throughput. The important property is that FLX can run hardware workloads and prove that the result matches the reference-model path exactly for the validated cases, while also preserving evidence and supporting controlled recovery.

That matters for physical-world simulation, robotics, factory-state replay, digital twins, and fault-recoverable compute, where being able to replay and validate state can be as important as raw execution speed.

The visual/media mapping for each benchmark case is recorded in [EVIDENCE_CORRELATION.md](EVIDENCE_CORRELATION.md).
