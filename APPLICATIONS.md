# Applications

FLX1.0 is aimed at deterministic workloads where state, replay, and validation matter.

## Robotics And Control

Robotics systems often need repeatable state evolution, sensor-state replay, fault diagnosis, and deterministic control loops.

Relevant FLX1.0 properties:

- deterministic workload execution;
- replayable state;
- controlled restore;
- reference-model comparison;
- world-grid and local-state workload support.

## Factory And Digital Twins

Factory systems involve queues, stations, jams, failures, recovery, and stateful process flow.

Relevant FLX1.0 properties:

- deterministic world-state updates;
- checkpoint and restore;
- repeatable failure replay;
- evidence generation;
- hardware-assisted local-state processing.

## Field And Physics Simulation

Grid and field workloads map naturally to deterministic lattice-style execution.

Relevant FLX1.0 properties:

- 1D, 2D, and 3D field support;
- fixed-point reference-model validation;
- wave-style propagation proof;
- particle-to-field regression proof.

## Fault-Recoverable Compute

Some systems need to know not only the final answer, but whether they can restore and continue from a known state.

Relevant FLX1.0 properties:

- controlled restore proof;
- baseline vs restored comparison;
- evidence bundle generation;
- deterministic replay.

## Workload Acceleration

The prototype also includes an adaptive dispatch concept: workloads can be routed toward a suitable execution path, including programmable fallback and accelerator-capable paths.

Current validated workload classes:

- field workloads;
- SHA-style deterministic compute;
- robotics/world-grid style workloads;
- generic programmable workloads.
