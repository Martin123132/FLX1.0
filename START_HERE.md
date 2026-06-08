# Start Here

This repository is a private FLX1.0 evidence pack.

The shortest review path is:

1. Open [README.md](README.md) for the headline summary.
2. Open [VALIDATION_RESULTS.md](VALIDATION_RESULTS.md) for the measured pass/fail results.
3. Open [EVIDENCE_CORRELATION.md](EVIDENCE_CORRELATION.md) to map each result to source files.
4. Open [MEDIA/evidence_panels/lattice_memory_layout_panel.png](MEDIA/evidence_panels/lattice_memory_layout_panel.png).
5. Open [MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png](MEDIA/evidence_panels/cpu_vs_flx_benchmark_panel.png).
6. Open [MEDIA/evidence_panels/adaptability_flash_boot_panel.png](MEDIA/evidence_panels/adaptability_flash_boot_panel.png).
7. Open [MEDIA/flx1_evidence_wall.png](MEDIA/flx1_evidence_wall.png).
8. Watch [MEDIA/videos/flx1_evidence_demo.mp4](MEDIA/videos/flx1_evidence_demo.mp4).
9. Check file hashes in [MEDIA/MEDIA_MANIFEST.json](MEDIA/MEDIA_MANIFEST.json) and the per-evidence `file_hashes_sha256.txt` files.

## Current Core Result

- Latest board acceptance date: **8 June 2026**
- Full acceptance: **PASS**
- 100T build/timing/MCS deployment: **PASS**
- Cmod config-memory deployment: **PASS**
- MTS 1D/2D/3D checks: **PASS**
- 1024-active-point checks: **PASS**
- 10M Particle3D regression: **PASS**
- Wave restore: **PASS**
- Controlled WAL/recovery: **PASS**
- Adaptive dispatch: **PASS**
- Lattice memory mapper/router: **PASS**
- CPU-vs-FLX benchmark comparison: **PASS**
- Flash-booted programmable adaptability suite: **PASS**

## Key Evidence Folders

- [evidence/acceptance_20260608_full](evidence/acceptance_20260608_full)
- [evidence/board_deployment_20260608](evidence/board_deployment_20260608)
- [evidence/lattice_memory_20260608](evidence/lattice_memory_20260608)
- [evidence/cpu_vs_flx_20260608](evidence/cpu_vs_flx_20260608)
- [evidence/adaptability_flash_boot_20260608](evidence/adaptability_flash_boot_20260608)
- [evidence/flx3d_generality_20260524](evidence/flx3d_generality_20260524)
- [MEDIA/evidence_panels](MEDIA/evidence_panels)
- [MEDIA/plots](MEDIA/plots)
- [MEDIA/report_screenshots](MEDIA/report_screenshots)
- [MEDIA/videos](MEDIA/videos)

## Fast Evidence Checks

| Claim | Source |
|---|---|
| Full suite passed | [evidence/acceptance_20260608_full/acceptance_summary.json](evidence/acceptance_20260608_full/acceptance_summary.json) |
| Boards were built/programmed/verified | [evidence/board_deployment_20260608/README.md](evidence/board_deployment_20260608/README.md) |
| Lattice mapper passed host and live board checks | [evidence/lattice_memory_20260608/lattice_memory_summary.json](evidence/lattice_memory_20260608/lattice_memory_summary.json) |
| CPU-style VM, SHA-256, and robot-grid paths matched references | [evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json](evidence/cpu_vs_flx_20260608/cpu_vs_flx_summary.json) |
| Flash-booted VM/load/Q16/reduction/world-state cases matched references | [evidence/adaptability_flash_boot_20260608/adaptability_summary.json](evidence/adaptability_flash_boot_20260608/adaptability_summary.json) |
| 10M Particle3D matched reference output | [evidence/acceptance_20260608_full/particle3d_438/compare_final_cpu_vs_fpga/compare_report.json](evidence/acceptance_20260608_full/particle3d_438/compare_final_cpu_vs_fpga/compare_report.json) |
| WAL restore matched baseline | [evidence/acceptance_20260608_full/fault_recovery](evidence/acceptance_20260608_full/fault_recovery) |
