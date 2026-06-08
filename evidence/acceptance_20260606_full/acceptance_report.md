# FLX Core Acceptance Report

- Final status: `PASS`
- Port: `COM5`
- Baud: `115200`
- Kernel contract: `0x4D545332`

## Board / Session Health

- Health pass: `Pass`
- Help/docs audit missing: `0`

## MTS 1D/2D/3D Results

- `mts_1d_100_t140`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`
- `mts_2d_16x16_t140`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`
- `mts_3d_8x8x8_t140`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`
- `mts_1d_1024_t2`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`
- `mts_2d_32x32_t2`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`
- `mts_3d_10x10x10_t2`: pass=`Pass`, mismatches=`0`, max_abs_delta_q16=`0`

## Invalid Config Rejection

- Pass: `Pass`

## Particle3D Regression

- Pass: `Pass`
- Particles: `10000000`
- Timesteps: `438`
- Mismatches: `0`
- Max abs delta Q16: `0`
- Normalized overlap: `1.0`

## Fault / Recovery Proof

- Pass: `Pass`
- Stage: `complete`

## Wave Propagation Restore Demo

- Pass: `Pass`
- Mismatches: `0`
- Max abs delta Q16: `0`
- Normalized overlap: `1.0`

## Adaptive Dispatcher

- Pass: `Pass`
- Cases: `4`
- `sha256_nonce_scan`: selected engine `sha_accel`, fallback `ukernel_vm`, pass `True`
- `robot_swarm_grid`: selected engine `robotics_accel`, fallback `ukernel_vm`, pass `True`
- `wave2d_restore`: selected engine `mts_full_physics`, fallback `ukernel_vm`, pass `True`
- `generic_program`: selected engine `ukernel_vm`, fallback `not required`, pass `True`

## RTL Simulation Proof

- Pass: `Pass`
- PASS line seen: `Pass`

## Benchmark Table

| case | dimension | shape | active_points | particles | timesteps | a7_cycles | wall_elapsed_s | mismatches | max_abs_delta_q16 | normalized_overlap | pass |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| mts_1d_100_t140 | 1d | 100x1x1 | 100 | 0 | 140 | 0 | not recorded | 0 | 0 | 1.0000000000000002 | Pass |
| mts_2d_16x16_t140 | 2d | 16x16x1 | 256 | 0 | 140 | 0 | not recorded | 0 | 0 | 0.9999999999999999 | Pass |
| mts_3d_8x8x8_t140 | 3d | 8x8x8 | 512 | 0 | 140 | 0 | not recorded | 0 | 0 | 0.9999999999999999 | Pass |
| mts_1d_1024_t2 | 1d | 1024x1x1 | 1024 | 0 | 2 | 0 | not recorded | 0 | 0 | 0.9999999999999998 | Pass |
| mts_2d_32x32_t2 | 2d | 32x32x1 | 1024 | 0 | 2 | 0 | not recorded | 0 | 0 | 1.0000000000000002 | Pass |
| mts_3d_10x10x10_t2 | 3d | 10x10x10 | 1000 | 0 | 2 | 0 | not recorded | 0 | 0 | 0.9999999999999999 | Pass |
| particle3d_438_10m | 3d_particle | 8x8x8 | 512 | 10000000 | 438 | not recorded | not recorded | 0 | 0 | 1.0 | Pass |
| wave_restore_2d | 2d_wave_restore | 4x4x1 | 256 | 1 | 32 | 20514 | 1.2456326999963494 | 0 | 0 | 1.0 | Pass |

## Raw Log Links

- `acceptance_runner.log`
- `uart_logs/health/uart_health.log`
- `uart_logs/invalid_config`
- `uart_logs/fault_recovery`
- `uart_logs/wave_restore_demo`
- `benchmark_reports/adaptive_dispatcher`
