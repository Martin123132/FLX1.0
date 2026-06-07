# Hardware Acceptance Evidence - 6 June 2026

This folder contains the generated artefacts from the passing FLX hardware acceptance run on 6 June 2026.

## Start Here

- [acceptance_report.md](acceptance_report.md) - human-readable acceptance report
- [acceptance_summary.json](acceptance_summary.json) - machine-readable acceptance summary
- [manifest.json](manifest.json) - evidence bundle manifest
- [file_hashes_sha256.txt](file_hashes_sha256.txt) - file-integrity hashes
- [acceptance_runner.log](acceptance_runner.log) - full runner log

## Result

Final acceptance status: **PASS**

Key pass results:

- MTS 1D/2D/3D validations passed.
- 1024-active-point capability checks passed.
- Invalid configuration rejection passed.
- Particle3D 10,000,000-particle / 438-step regression passed.
- reference-vs-hardware comparisons passed with zero fixed-point mismatches for validated cases.
- Controlled restore/recovery proof passed.
- Wave restore demo passed.
- Adaptive dispatcher proof passed.
- RTL simulation proof passed.

## Folder Map

| Folder | Contents |
|---|---|
| [benchmark_reports](benchmark_reports) | Per-case benchmark outputs, metrics, reports, plots, and generated result files |
| [compare_reports](compare_reports) | reference-vs-hardware comparison reports and mismatch/error artefacts |
| [plots](plots) | Generated plots and plot summaries |
| [uart_logs](uart_logs) | Raw board/UART logs and recovery/wave run evidence |
| [rtl_logs](rtl_logs) | RTL simulation logs used by the acceptance gate |

## Important Artefacts

Particle3D regression:

- [benchmark_reports/particle3d_438](benchmark_reports/particle3d_438)
- [compare_reports/particle3d_438](compare_reports/particle3d_438)

MTS field validation:

- [benchmark_reports/mts](benchmark_reports/mts)
- [compare_reports/mts](compare_reports/mts)
- [plots/mts](plots/mts)

Controlled restore and wave demo:

- [uart_logs/fault_recovery](uart_logs/fault_recovery)
- [uart_logs/wave_restore_demo](uart_logs/wave_restore_demo)
- [plots/wave_restore_demo](plots/wave_restore_demo)

Adaptive dispatch:

- [benchmark_reports/adaptive_dispatcher](benchmark_reports/adaptive_dispatcher)

## Evidence Scope

This archive is the hardware acceptance evidence set for the passing run. It includes the generated proof artefacts needed to inspect the result: reports, logs, comparisons, benchmark outputs, plots, and manifests.
