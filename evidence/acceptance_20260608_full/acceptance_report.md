# FLX1.0 Core CPU Acceptance Report

- Final PASS: `True`
- Port: `COM5`
- Baud: `115200`
- Kernel contract: `0x4D545332`

## Board / Session Health

- Health pass: `True`
- Help/docs audit missing: `0`

## MTS 1D/2D/3D Results

- `mts_1d_100_t140` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_1d_100_t140`
- `mts_2d_16x16_t140` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_2d_16x16_t140`
- `mts_3d_8x8x8_t140` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_3d_8x8x8_t140`
- `mts_1d_1024_t2` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_1d_1024_t2`
- `mts_2d_32x32_t2` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_2d_32x32_t2`
- `mts_3d_10x10x10_t2` pass=`True` mismatches=`0` max_abs_delta_q16=`0` path=`E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\mts\mts_3d_10x10x10_t2`

## Invalid Config Rejection

- Pass: `True`

## Particle3D Regression

- Pass: `True`
- Cmod mirror: `True`

## Fault / Recovery Proof

- Pass: `True`
- Stage: `complete`

## Wave Propagation Restore Demo

- Pass: `True`
- Path: `E:\GMW_CPU\results\board_acceptance\20260608_135515\acceptance\wave_restore_demo`

## Adaptive Dispatcher

- Pass: `True`
- Cases: `4`

## RTL Simulation Proof

- Pass: `True`
- PASS line seen: `True`

## Benchmark Table

| case | dimension | shape | active_points | particles | timesteps | a7_cycles | wall_elapsed_s | cycles_per_point | cycles_per_point_step | mismatches | max_abs_delta_q16 | normalized_overlap | pass |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| mts_1d_100_t140 | 1d | 100x1x1 | 100 | 1 | 140 | 355006 | 0.20729509999910078 | 3550.06 | 25.35757142857143 | 0 | 0 | 1.0000000000000002 | True |
| mts_2d_16x16_t140 | 2d | 16x16x1 | 256 | 1 | 140 | 1094658 | 0.21114289999968605 | 4276.0078125 | 30.542912946428572 | 0 | 0 | 0.9999999999999999 | True |
| mts_3d_8x8x8_t140 | 3d | 8x8x8 | 512 | 1 | 140 | 2600730 | 0.20649589999993623 | 5079.55078125 | 36.282505580357146 | 0 | 0 | 0.9999999999999999 | True |
| mts_1d_1024_t2 | 1d | 1024x1x1 | 1024 | 1 | 2 | 52480 | 0.2065734000007069 | 51.25 | 25.625 | 0 | 0 | 0.9999999999999998 | True |
| mts_2d_32x32_t2 | 2d | 32x32x1 | 1024 | 1 | 2 | 64770 | 0.207304399998975 | 63.251953125 | 31.6259765625 | 0 | 0 | 1.0000000000000002 | True |
| mts_3d_10x10x10_t2 | 3d | 10x10x10 | 1000 | 1 | 2 | 75286 | 0.20667369999864604 | 75.286 | 37.643 | 0 | 0 | 0.9999999999999999 | True |
| particle3d_438_10m | 3d_particle | 8x8x8 | 512 | 10000000 | 438 | None | None | None | None | None | None | None | True |
| wave_restore_2d | 2d_wave_restore | 4x4x1 | 256 | 1 | 32 | 20514 | 1.2232624999996915 | None | None | 0 | 0 | 1.0 | True |

## Raw Log Links

- `acceptance_runner.log`
- `health/uart_health.log`
- `invalid_config/uart_invalid_config.log`
- `fault_recovery/uart_fault_recovery.log`
- `wave_restore_demo/uart_wave_restore.log`
- `adaptive_dispatcher/*_dispatch_plan.json`
