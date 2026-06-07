# FLX1.0 Video Storyboard

This is a suggested short-form review video flow using only the evidence and media in this repository.

## 1. Opening

Show:

- `public_presentation_thumbnail.png`
- `architecture_overview.png`

Narration:

FLX1.0 is a deterministic finite-lattice hardware compute prototype. The evidence run shows configured hardware workloads, matched reference-model runs, comparison reports, plots, and controlled restore/recovery evidence.

## 2. Hardware Workload Run

Show:

- `experiment_evidence_wall.png`
- `plots/mts_1d_100_t140_profile.png`
- `plots/mts_2d_16x16_t140_density.png`
- `plots/mts_3d_8x8x8_t140_density_mid_z.png`

Narration:

The acceptance suite covers configurable 1D, 2D, and 3D field workloads. It also includes 1024-active-point capability checks.

## 3. Reference-Model Comparison

Show:

- `cards/validation_result_card.png`
- `plots/particle3d_10m_438_slice_xy.png`
- `plots/particle3d_reference_slice_xy.png`

Narration:

The Particle3D regression runs a 10,000,000-particle, 438-step deterministic workload. Hardware output and reference-model output are compared under a fixed-point contract. The validated comparisons report zero mismatches and zero maximum Q16 delta.

## 4. Restore And Recovery

Show:

- `plots/wave_restore_density.png`
- `plots/wave_restore_real.png`
- `cards/validation_result_card.png`

Narration:

The acceptance evidence includes a controlled restore/recovery path. The restored run is compared against the baseline/reference evidence so the recovery path is not just asserted; it is checked.

## 5. Evidence Archive

Show:

- `../evidence/acceptance_20260606_full/acceptance_report.md`
- `../evidence/acceptance_20260606_full/acceptance_summary.json`
- `MEDIA_MANIFEST.json`

Narration:

The repository includes the evidence archive: reports, UART logs, benchmark reports, comparison JSON, result CSVs, generated plots, RTL simulation logs, and SHA-256 manifests.

## Closing Claim

FLX1.0 demonstrates a deterministic hardware compute fabric that can run multiple finite-lattice workloads, compare hardware results against a reference model, preserve evidence, and demonstrate controlled recovery behavior.
