# Result Summary

The FLX1.0 prototype completed a full hardware acceptance run on **6 June 2026**.

The acceptance run tested the fabric as a deterministic processing system, not as a single fixed demo. It covered field workloads, particle workloads, recovery behavior, adaptive dispatch, reporting, plotting, and CPU-reference comparison.

The generated evidence archive is stored in [evidence/acceptance_20260606_full](evidence/acceptance_20260606_full/).

## Summary Table

| Test Area | What Was Tested | Result |
|---|---|---:|
| Startup and health | hardware boot, link health, status reporting | Pass |
| Field workloads | configurable 1D, 2D, and 3D field cases | Pass |
| Capacity checks | active logical fields up to 1024 points | Pass |
| Invalid input checks | rejected invalid workload configurations | Pass |
| Particle regression | 10,000,000-particle 3D run, 438 steps | Pass |
| CPU comparison | hardware result vs fixed-point CPU-reference result | Pass |
| Restore proof | controlled restore path vs baseline and CPU reference | Pass |
| Wave demo | 2D wave-style propagation with restore | Pass |
| Adaptive dispatch | field, SHA-style, robotics-style, generic workload classes | Pass |
| RTL simulation | hardware kernel simulation proof | Pass |
| Evidence generation | reports, plots, summaries, evidence bundle | Pass |

## Headline Result

The strongest validated result is the 10,000,000-particle 3D regression:

| Metric | Result |
|---|---:|
| Particles | 10,000,000 |
| Steps | 438 |
| Field type | 3D |
| CPU-reference comparison | Pass |
| Final field mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Normalized overlap | 1.0 |
| Hardware mirror verification | Pass |

## Field Workload Result

The acceptance run validated configurable field workloads:

| Case | Public Scale | Result |
|---|---:|---:|
| 1D field | 100 active points, extended run | Pass |
| 2D field | 16 x 16 active field, extended run | Pass |
| 3D field | 8 x 8 x 8 active field, extended run | Pass |
| 1D capacity check | 1024 active points | Pass |
| 2D capacity check | 32 x 32 active field | Pass |
| 3D capacity check | 10 x 10 x 10 active field | Pass |

For the validated comparisons, the final fixed-point mismatch count was **0** and the maximum fixed-point delta was **0**.

## Recovery Result

The controlled restore proof compared:

- CPU reference vs hardware baseline;
- CPU reference vs restored hardware run;
- hardware baseline vs restored hardware run.

Result:

| Metric | Result |
|---|---:|
| Restore comparison | Pass |
| Final baseline comparison | Pass |
| Fixed-point mismatches | 0 |
| Maximum fixed-point delta | 0 |
| Normalized overlap | 1.0 |

This result is the controlled restore/recovery proof. Physical power-interruption testing is tracked as a separate hardware acceptance step.

## Adaptive Dispatch Result

The adaptive dispatcher selected workload paths for:

- field/wave workload;
- SHA-style deterministic workload;
- robotics/world-grid style workload;
- generic programmable workload.

Result: **pass**.
