# FLX1.0 Media Evidence

This folder contains presentation media generated from the evidence CSV/JSON/log artefacts in `evidence/`.

Each evidence panel is intended to show what was tested, the measured result, the pass/fail metrics, and the source artefacts used.

## Required Review Media

- Architecture overview: [architecture_overview.png](architecture_overview.png)
- Evidence wall: [flx1_evidence_wall.png](flx1_evidence_wall.png)
- Public presentation thumbnail: [public_presentation_thumbnail.png](public_presentation_thumbnail.png)
- Short evidence video: [videos/flx1_evidence_demo.mp4](videos/flx1_evidence_demo.mp4)
- Lattice memory proof panel: [evidence_panels/lattice_memory_layout_panel.png](evidence_panels/lattice_memory_layout_panel.png)
- CPU-vs-FLX benchmark panel: [evidence_panels/cpu_vs_flx_benchmark_panel.png](evidence_panels/cpu_vs_flx_benchmark_panel.png)
- Flash-boot adaptability panel: [evidence_panels/adaptability_flash_boot_panel.png](evidence_panels/adaptability_flash_boot_panel.png)

## Evidence Panels

- [evidence_panels/mts_1d_100_t140_panel.png](evidence_panels/mts_1d_100_t140_panel.png)
- [evidence_panels/mts_1d_1024_t2_panel.png](evidence_panels/mts_1d_1024_t2_panel.png)
- [evidence_panels/mts_2d_16x16_t140_panel.png](evidence_panels/mts_2d_16x16_t140_panel.png)
- [evidence_panels/mts_2d_32x32_t2_panel.png](evidence_panels/mts_2d_32x32_t2_panel.png)
- [evidence_panels/mts_3d_8x8x8_t140_panel.png](evidence_panels/mts_3d_8x8x8_t140_panel.png)
- [evidence_panels/mts_3d_10x10x10_t2_panel.png](evidence_panels/mts_3d_10x10x10_t2_panel.png)
- [evidence_panels/particle3d_10m_438_panel.png](evidence_panels/particle3d_10m_438_panel.png)
- [evidence_panels/flx3d_generality_delta_field_panel.png](evidence_panels/flx3d_generality_delta_field_panel.png)
- [evidence_panels/flx3d_generality_gaussian_field_panel.png](evidence_panels/flx3d_generality_gaussian_field_panel.png)
- [evidence_panels/flx3d_generality_plane_wave_field_panel.png](evidence_panels/flx3d_generality_plane_wave_field_panel.png)
- [evidence_panels/flx3d_generality_random_field_panel.png](evidence_panels/flx3d_generality_random_field_panel.png)
- [evidence_panels/wave_restore_panel.png](evidence_panels/wave_restore_panel.png)
- [evidence_panels/fault_recovery_panel.png](evidence_panels/fault_recovery_panel.png)
- [evidence_panels/adaptive_dispatch_panel.png](evidence_panels/adaptive_dispatch_panel.png)
- [evidence_panels/lattice_memory_layout_panel.png](evidence_panels/lattice_memory_layout_panel.png)
- [evidence_panels/cpu_vs_flx_benchmark_panel.png](evidence_panels/cpu_vs_flx_benchmark_panel.png)
- [evidence_panels/adaptability_flash_boot_panel.png](evidence_panels/adaptability_flash_boot_panel.png)
- [evidence_panels/adaptability_post_rtl_build_panel.png](evidence_panels/adaptability_post_rtl_build_panel.png)

## Lattice Layout Plots

These images show the memory-ordering proof for row-major compatibility, serpentine/snake mapping, and Morton/Z-order mapping:

- [plots/lattice_layout_2d_32x32_row_snake_morton.png](plots/lattice_layout_2d_32x32_row_snake_morton.png)
- [plots/lattice_layout_3d_8x8x8_row_snake_morton.png](plots/lattice_layout_3d_8x8x8_row_snake_morton.png)
- [plots/lattice_layout_3d_10x10x10_row_snake_morton.png](plots/lattice_layout_3d_10x10x10_row_snake_morton.png)

The source evidence is [../evidence/lattice_memory_20260608/lattice_memory_summary.json](../evidence/lattice_memory_20260608/lattice_memory_summary.json).

## Reading The Panels

- **FLX hardware** is the output dumped from the FPGA run artefacts.
- **Reference model** is the fixed-point architecture/reference run for the same workload.
- **ZERO Q16 ERROR** means every compared fixed-point sample matched exactly.
- **Layout proof** means logical coordinates mapped to the same local indices in host checks and live board `layout-map` responses.
- **CPU-vs-FLX benchmark** separates A7 kernel-cycle throughput from UART wall-rate and only marks a case as passed when the FLX result matches the CPU/reference result exactly.
- **Flash-boot adaptability** shows live hardware results for VM RAM-load, Q16, integer bitwork, reductions, lattice-neighbour addressing, and world-state local-rule cases after rebuilding the current A7 RTL, programming the A7-100T MCS into config flash, and booting from configuration memory.
- MTS contract word shown on panels: `0x4D545332`.

## Source Integrity

[MEDIA_MANIFEST.json](MEDIA_MANIFEST.json) records SHA-256 hashes for generated media files.
