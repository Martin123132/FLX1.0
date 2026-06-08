# Architecture Overview

FLX1.0 (Finite Lattice maXimus) is a deterministic finite-lattice processing fabric. It is built around the idea that hardware workloads should be:

- explicitly configured;
- deterministic;
- comparable against a reference model;
- capable of producing evidence;
- recoverable through controlled state restoration.

## Architecture Model

```mermaid
flowchart TB
    A["Operator / host"] --> B["Configuration and orchestration"]
    B --> C["Deterministic compute fabric"]
    C --> D["Field workloads"]
    C --> E["Particle workloads"]
    C --> F["World-state workloads"]
    C --> G["Programmable workload path"]
    C --> H["Checkpoint / restore path"]
    D --> I["reference-model comparison"]
    E --> I
    F --> I
    G --> I
    H --> I
    I --> J["Evidence bundle"]
```

## Execution Model

At a system level, a FLX run follows this pattern:

```mermaid
sequenceDiagram
    participant User
    participant FLX as FLX prototype
    participant reference model as reference model
    participant Evidence

    User->>FLX: define workload
    User->>reference model: define same workload
    FLX->>FLX: run hardware path
    reference model->>reference model: run reference path
    FLX->>Evidence: export hardware result
    reference model->>Evidence: export reference result
    Evidence->>Evidence: compare outputs
    Evidence->>User: report pass/fail and metrics
```

## Current Capability

The current prototype has validated:

- configurable 1D, 2D, and 3D field workloads;
- particle-to-field accumulation;
- wave-style propagation and restore;
- controlled restore/recovery;
- adaptive workload dispatch;
- reference-model validation;
- report and plot generation.

## Direction

The same architecture direction can be extended toward:

- deterministic robotics simulation;
- factory-state replay;
- digital-twin state engines;
- fixed-point physics and field simulation;
- recoverable embedded compute;
- workload-specific hardware acceleration.
