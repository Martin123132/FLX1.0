# FLX CPU-vs-Lattice Benchmark

- Port: `COM5`
- Baud: `115200`
- Final pass: `True`
- A7 clock assumption for kernel-cycle rates: `100000000 Hz`

## Benchmark Table

| Case | Metric | CPU rate | FLX kernel rate | FLX wall rate | FLX/CPU kernel ratio | Correct |
|---|---|---:|---:|---:|---:|---:|
| vm_sum4 | words_per_second | 245398.767 | 14814814.815 | 1.983 | 60.370 | True |
| sha256_nonce_scan | hashes_per_second | 140819.407 | 829470.504 | 7236.157 | 5.890 | True |
| robot_grid_world_state | cell_steps_per_second | 3883200.597 | 16407626.983 | 1454.168 | 4.225 | True |

## Interpretation

The CPU rate is measured on the host Python reference. The FLX kernel rate is calculated from hardware cycle counters and excludes UART/control loading overhead. The FLX wall rate includes serial control overhead and is useful for operator-run cost, not raw fabric throughput.

The normal CPU-style cases are SHA-256 nonce scan and integer reduction. The FLX-specific cases are local-state grid acceleration plus the linked acceptance evidence for MTS field evolution, WAL restore, and lattice layout mapping.

## Source Files

- `cpu_vs_flx_summary.json`
- `cpu_vs_flx_benchmark.csv`
- `uart_cpu_vs_flx.log`
- `cpu_vs_flx_throughput.png`
