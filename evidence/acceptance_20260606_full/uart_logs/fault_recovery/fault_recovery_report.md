# Fault / Recovery Acceptance

- Final pass: `True`
- Stage: `complete`
- Checkpoint restore mismatches: `0`
- Final baseline mismatches: `0`
- UART log: `uart_fault_recovery.log`

This is a controlled WAL recovery proof using existing Z7/A7/Cmod commands.
The default automated proof stages a deterministic MTS state into Cmod WAL_VAR, restores it to A7, reruns, and compares bit-exactly.
The legacy fixed-lattice flash checkpoint path remains available with `--mode fixed-lattice` for diagnosis.
It is not a manual physical power-removal test; that remains a separate hardware acceptance step.
