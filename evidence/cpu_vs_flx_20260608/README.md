# CPU-vs-FLX Hardware Benchmark - 8 June 2026

This folder contains the live COM5 evidence for a CPU-reference comparison against FLX1.0 hardware paths.

Files:

- `cpu_vs_flx_summary.json` - structured pass/fail, rates, hashes/counters.
- `cpu_vs_flx_benchmark.csv` - benchmark table.
- `cpu_vs_flx_report.md` - readable summary.
- `uart_cpu_vs_flx.log` - raw live board transcript.
- `plot_error.txt` - notes why Matplotlib plot generation was replaced by the PIL evidence panel.

Result: `final_pass=true`. The generic VM integer reduction, SHA-256 nonce scan, and robot/world-grid update all matched their CPU references exactly.
