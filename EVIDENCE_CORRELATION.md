# FLX1.0 Evidence Correlation

This file maps the presentation material to the evidence files in the repository.

Use this page to answer: what was tested, what passed, what visual shows it, and where the source artefacts are.

## Current Evidence Set

Latest validated hardware run: **8 June 2026**

| Evidence Area | Source | Result |
|---|---|---:|
| Full acceptance suite | [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json) | Pass |
| Board build/program/verify | [evidence/board_deployment_20260608/README.md](evidence/board_deployment_20260608/README.md) | Pass |
| Lattice memory mapper/router | [evidence/lattice_memory_20260608/lattice_memory_summary.json](evidence/lattice_memory_20260608/lattice_memory_summary.json) | Pass |
| CPU-vs-FLX benchmark | [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json) | Pass |
| Flash-booted programmable adaptability suite | [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json) | Pass |
| Earlier dense 3D generality set | [evidence/flx3d_generality_20260524/summary.json](evidence/flx3d_generality_20260524/summary.json) | Pass |

## Presentation Files

- Evidence video: [MEDIA/videos/flx1_evidence_demo.mp4](MEDIA/videos/flx1_evidence_demo.mp4)
- Evidence wall: [MEDIA/flx1_evidence_wall.png](MEDIA/flx1_evidence_wall.png)
- Presentation thumbnail: [MEDIA/public_presentation_thumbnail.png](MEDIA/public_presentation_thumbnail.png)
- Lattice memory proof panel: [MEDIA/evidence_panels/lattice_memory_layout_panel.png](MEDIA/evidence_panels/lattice_memory_layout_panel.png)
- CPU-vs-FLX benchmark panel: [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png)
- Flash-boot adaptability panel: [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png)
- Media hashes: [MEDIA/MEDIA_MANIFEST.json](MEDIA/MEDIA_MANIFEST.json)

## Board Deployment Evidence

| Gate | Source Artefact | Result |
|---|---|---:|
| 100T implementation timing | [build_100t_result_accum_fix_20260608_125049.log](evidence/board_deployment_20260608/build_100t_result_accum_fix_20260608_125049.log) | `ROUTED_WNS=0.134`, Pass |
| 100T config-memory program/verify | [program_100t_cfgmem_result_accum_fix_retry_20260608.log](evidence/board_deployment_20260608/program_100t_cfgmem_result_accum_fix_retry_20260608.log) | Pass |
| Cmod config-memory program/verify | [program_cmod_35t_cfgmem_20260608.log](evidence/board_deployment_20260608/program_cmod_35t_cfgmem_20260608.log) | Pass |
| Live board acceptance stdout | [board_acceptance_20260608_135515.stdout.log](evidence/board_deployment_20260608/board_acceptance_20260608_135515.stdout.log) | Pass |

Key live-board lines in the stdout log include `SPI1 (A7): OK`, `SPI0 (Cmod): OK`, `CMOD MIRROR PASS`, `Checkpoint flash commit completed`, and `[ACCEPTANCE] final_pass=True`.

## Main Acceptance Cases

### MTS 1D, 100 Points, 140 Steps

- Result: PASS
- Shape: `100x1x1`
- Active points: `100`
- A7 cycles: `355006`
- Mismatches: `0`
- Max Q16 delta: `0`
- Overlap: `1.0000000000000002`
- Panel: [MEDIA/evidence_panels/mts_1d_100_t140_panel.png](MEDIA/evidence_panels/mts_1d_100_t140_panel.png)
- Evidence: [evidence/acceptance_20260608_full/mts/mts_1d_100_t140](evidence/acceptance_20260608_full/mts/mts_1d_100_t140)

### MTS 2D, 16x16, 140 Steps

- Result: PASS
- Shape: `16x16x1`
- Active points: `256`
- A7 cycles: `1094658`
- Mismatches: `0`
- Max Q16 delta: `0`
- Overlap: `0.9999999999999999`
- Panel: [MEDIA/evidence_panels/mts_2d_16x16_t140_panel.png](MEDIA/evidence_panels/mts_2d_16x16_t140_panel.png)
- Evidence: [evidence/acceptance_20260608_full/mts/mts_2d_16x16_t140](evidence/acceptance_20260608_full/mts/mts_2d_16x16_t140)

### MTS 3D, 8x8x8, 140 Steps

- Result: PASS
- Shape: `8x8x8`
- Active points: `512`
- A7 cycles: `2600730`
- Mismatches: `0`
- Max Q16 delta: `0`
- Overlap: `0.9999999999999999`
- Panel: [MEDIA/evidence_panels/mts_3d_8x8x8_t140_panel.png](MEDIA/evidence_panels/mts_3d_8x8x8_t140_panel.png)
- Evidence: [evidence/acceptance_20260608_full/mts/mts_3d_8x8x8_t140](evidence/acceptance_20260608_full/mts/mts_3d_8x8x8_t140)

### 1024-Point Capability Checks

| Case | Result | Shape | Cycles | Mismatches | Max Delta | Panel |
|---|---:|---:|---:|---:|---:|---|
| 1D cap | Pass | 1024 x 1 x 1 | 52480 | 0 | 0 | [panel](MEDIA/evidence_panels/mts_1d_1024_t2_panel.png) |
| 2D cap | Pass | 32 x 32 x 1 | 64770 | 0 | 0 | [panel](MEDIA/evidence_panels/mts_2d_32x32_t2_panel.png) |
| 3D cap | Pass | 10 x 10 x 10 | 75286 | 0 | 0 | [panel](MEDIA/evidence_panels/mts_3d_10x10x10_t2_panel.png) |

Source: [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json)

### 10M Particle Regression

- Result: PASS
- Workload: `10,000,000` particles, `438` steps
- Shape: `8x8x8`
- Mismatches: `0`
- Max Q16 delta: `0`
- Overlap: `1.0`
- Cmod mirror verified: `true`
- Panel: [MEDIA/evidence_panels/particle3d_10m_438_panel.png](MEDIA/evidence_panels/particle3d_10m_438_panel.png)
- Evidence: [evidence/acceptance_20260608_full/particle3d_438](evidence/acceptance_20260608_full/particle3d_438)

## Lattice Memory Mapper And Router

- Result: PASS
- Host mapping checks: `48 / 48`
- Live board checks: `51 / 51`
- Layouts: `row`, `snake`, `morton`
- Logical cap tested: `1024` active points
- Live board path: COM5 at 115200
- Panel: [MEDIA/evidence_panels/lattice_memory_layout_panel.png](MEDIA/evidence_panels/lattice_memory_layout_panel.png)
- Evidence: [evidence/lattice_memory_20260608](evidence/lattice_memory_20260608)

Visual maps:

- [MEDIA/plots/lattice_layout_2d_32x32_row_snake_morton.png](MEDIA/plots/lattice_layout_2d_32x32_row_snake_morton.png)
- [MEDIA/plots/lattice_layout_3d_8x8x8_row_snake_morton.png](MEDIA/plots/lattice_layout_3d_8x8x8_row_snake_morton.png)
- [MEDIA/plots/lattice_layout_3d_10x10x10_row_snake_morton.png](MEDIA/plots/lattice_layout_3d_10x10x10_row_snake_morton.png)

## Dense 3D Generality Cases

These are visually dense field cases retained from the earlier evidence set. Each is an `8x8x8` field with `512` active points and zero fixed-point mismatches.

| Case | Result | Panel | Evidence |
|---|---:|---|---|
| Delta field | Pass | [panel](MEDIA/evidence_panels/flx3d_generality_delta_field_panel.png) | [source](evidence/flx3d_generality_20260524/delta_field) |
| Gaussian field | Pass | [panel](MEDIA/evidence_panels/flx3d_generality_gaussian_field_panel.png) | [source](evidence/flx3d_generality_20260524/gaussian_field) |
| Plane-wave field | Pass | [panel](MEDIA/evidence_panels/flx3d_generality_plane_wave_field_panel.png) | [source](evidence/flx3d_generality_20260524/plane_wave_field) |
| Seeded-random field | Pass | [panel](MEDIA/evidence_panels/flx3d_generality_random_field_panel.png) | [source](evidence/flx3d_generality_20260524/random_field) |

## CPU-vs-FLX Benchmark

- Result: PASS
- Live board path: COM5 at 115200
- Panel: [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png)
- Report screenshot: [MEDIA/report_screenshots/cpu_vs_flx_report_screenshot.png](MEDIA/report_screenshots/cpu_vs_flx_report_screenshot.png)
- Evidence: [evidence/cpu_vs_flx_20260608](evidence/cpu_vs_flx_20260608)
- Raw UART transcript: [evidence/cpu_vs_flx_20260608/uart_cpu_vs_flx.log](evidence/cpu_vs_flx_20260608/uart_cpu_vs_flx.log)

| Case | CPU Reference Rate | FLX Kernel Rate | FLX/CPU Kernel Ratio | Exact Match |
|---|---:|---:|---:|---:|
| Generic VM integer sum | 245398.767 words/s | 14814814.815 words/s | 60.370x | Pass |
| SHA-256 nonce scan | 140819.407 hashes/s | 829470.504 hashes/s | 5.890x | Pass |
| Robot/world-grid update | 3883200.597 cell-steps/s | 16407626.983 cell-steps/s | 4.225x | Pass |

Source: [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json)

## Flash-Booted Programmable Adaptability

- Result: PASS
- Live board path: COM5 at 115200
- Build gate: current-source A7-100T implementation passed with `WNS=0.239 ns`, `TNS=0`
- Program path for this run: `config_100t.mcs` programmed and verified in A7-100T configuration flash
- Reset/boot path: `boot_hw_device`, Done pin HIGH, then COM5 test
- Panel: [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png)
- Evidence: [evidence/adaptability_flash_boot_20260608](evidence/adaptability_flash_boot_20260608)
- Raw UART transcript: [evidence/adaptability_flash_boot_20260608/uart_adaptability.log](evidence/adaptability_flash_boot_20260608/uart_adaptability.log)
- Flash programming log: [evidence/adaptability_flash_boot_20260608/program_100t_post_rtl_flash_20260608.log](evidence/adaptability_flash_boot_20260608/program_100t_post_rtl_flash_20260608.log)

| Case | Workload Type | CPU Expected | FLX Result | Exact Match |
|---|---|---:|---:|---:|
| `vm_load_xor_bitwork` | VM RAM load + integer bitwork | `0xB791F3DD` | `0xB791F3DD` | Pass |
| `vm_q16_multiply_load` | VM RAM load + Q16 fixed-point multiply | `0xFFFFA000` | `0xFFFFA000` | Pass |
| `vm_rotr_bit_permutation` | VM integer bit permutation | `0x78123456` | `0x78123456` | Pass |
| `vm_filter_count_reduce` | database/filter count reduction | `0x00000004` | `0x00000004` | Pass |
| `vm_checksum_xor_reduce` | checksum XOR reduction | `0x6633423D` | `0x6633423D` | Pass |
| `vm_signed_min_reduce` | signed minimum scan | `0xFFFFFFEC` | `0xFFFFFFEC` | Pass |
| `vm_signed_max_reduce` | signed maximum scan | `0x00000005` | `0x00000005` | Pass |
| `vm_lattice_neighbor_index` | lattice neighbour addressing | `0x0000000B` | `0x0000000B` | Pass |
| `sand_fall_local_rules` | local-rule world-state update | `0x0534C9FA` | `0x0534C9FA` | Pass |
| `factory_conveyor_jam` | factory/conveyor jam propagation | `0x5C4FA6A5` | `0x5C4FA6A5` | Pass |
| `swarm_wrap_edges` | wrapped-edge swarm/collision update | `0x894C99C6` | `0x894C99C6` | Pass |

## Recovery And Dispatch

### Wave Restore

- Result: PASS
- Shape: `4x4x1`
- Timesteps: `32`
- Mismatches: `0`
- Max Q16 delta: `0`
- Overlap: `1.0`
- Panel: [MEDIA/evidence_panels/wave_restore_panel.png](MEDIA/evidence_panels/wave_restore_panel.png)
- Evidence: [evidence/acceptance_20260608_full/wave_restore_demo](evidence/acceptance_20260608_full/wave_restore_demo)

### Controlled WAL Recovery

- Result: PASS
- Checkpoint restore mismatches: `0`
- Final restored run vs baseline mismatches: `0`
- Panel: [MEDIA/evidence_panels/fault_recovery_panel.png](MEDIA/evidence_panels/fault_recovery_panel.png)
- Evidence: [evidence/acceptance_20260608_full/fault_recovery](evidence/acceptance_20260608_full/fault_recovery)

### Adaptive Dispatch

- Result: PASS
- Workload classes: SHA-style deterministic compute, robotics/world-grid, wave/field, generic programmable path
- Panel: [MEDIA/evidence_panels/adaptive_dispatch_panel.png](MEDIA/evidence_panels/adaptive_dispatch_panel.png)
- Evidence: [evidence/acceptance_20260608_full/adaptive_dispatcher](evidence/acceptance_20260608_full/adaptive_dispatcher)

## Report Screenshots

- Acceptance report: [MEDIA/report_screenshots/acceptance_report_screenshot.png](MEDIA/report_screenshots/acceptance_report_screenshot.png)
- Benchmark table: [MEDIA/report_screenshots/benchmark_table_screenshot.png](MEDIA/report_screenshots/benchmark_table_screenshot.png)
- Validation card: [MEDIA/report_screenshots/validation_card_screenshot.png](MEDIA/report_screenshots/validation_card_screenshot.png)
- Fault recovery report: [MEDIA/report_screenshots/fault_recovery_report_screenshot.png](MEDIA/report_screenshots/fault_recovery_report_screenshot.png)
- Evidence manifest: [MEDIA/report_screenshots/evidence_manifest_screenshot.png](MEDIA/report_screenshots/evidence_manifest_screenshot.png)
- CPU-vs-FLX report: [MEDIA/report_screenshots/cpu_vs_flx_report_screenshot.png](MEDIA/report_screenshots/cpu_vs_flx_report_screenshot.png)

## Integrity Files

- Media hashes: [MEDIA/MEDIA_MANIFEST.json](MEDIA/MEDIA_MANIFEST.json)
- 8 June acceptance hashes: [evidence/acceptance_20260608_full/file_hashes_sha256.txt](evidence/acceptance_20260608_full/file_hashes_sha256.txt)
- 8 June board deployment hashes: [evidence/board_deployment_20260608/file_hashes_sha256.txt](evidence/board_deployment_20260608/file_hashes_sha256.txt)
- 8 June lattice memory hashes: [evidence/lattice_memory_20260608/file_hashes_sha256.txt](evidence/lattice_memory_20260608/file_hashes_sha256.txt)
- 8 June CPU-vs-FLX hashes: [evidence/cpu_vs_flx_20260608/file_hashes_sha256.txt](evidence/cpu_vs_flx_20260608/file_hashes_sha256.txt)
- 8 June flash-boot adaptability hashes: [evidence/adaptability_flash_boot_20260608/file_hashes_sha256.txt](evidence/adaptability_flash_boot_20260608/file_hashes_sha256.txt)
- Prior 3D generality hashes: [evidence/flx3d_generality_20260524/file_hashes_sha256.txt](evidence/flx3d_generality_20260524/file_hashes_sha256.txt)
