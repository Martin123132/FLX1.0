# FLX1.0 Presentation Media

This folder contains presentation-ready media generated from the FLX1.0 hardware acceptance evidence archive.

Source evidence folder:

- [`../evidence/acceptance_20260606_full`](../evidence/acceptance_20260606_full/README.md)

These files support quick technical review of the acceptance evidence.

## Primary Visuals

| File | Purpose |
|---|---|
| [`architecture_overview.png`](architecture_overview.png) | High-level evidence flow: operator, FLX1.0 hardware run, reference-model run, comparison, plots, and restore path. |
| [`cards/validation_result_card.png`](cards/validation_result_card.png) | Single-slide validation result card showing acceptance status, validated workload classes, zero-mismatch result, restore proof, and hash manifest coverage. |
| [`experiment_evidence_wall.png`](experiment_evidence_wall.png) | Wall-style collage of representative plots from each validated experiment class. |
| [`public_presentation_thumbnail.png`](public_presentation_thumbnail.png) | Thumbnail suitable for a private presentation/video cover. |
| [`MEDIA_MANIFEST.json`](MEDIA_MANIFEST.json) | SHA-256 hashes and sizes for every media file in this folder. |

## Plot Screenshots

The files in [`plots/`](plots/) are copied from generated acceptance reports:

| Plot | Evidence case |
|---|---|
| `mts_1d_100_t140_profile.png` | Configurable 1D field workload, 100 active points, 140 timesteps. |
| `mts_1d_1024_t2_profile.png` | 1D 1024-active-point capability check. |
| `mts_2d_16x16_t140_density.png` | Configurable 2D field workload, 16x16, 140 timesteps. |
| `mts_2d_32x32_t2_density.png` | 2D 1024-active-point capability check. |
| `mts_3d_8x8x8_t140_density_mid_z.png` | Configurable 3D field workload, 8x8x8, 140 timesteps. |
| `mts_3d_10x10x10_t2_density_mid_z.png` | 3D 1000-active-point capability check. |
| `particle3d_10m_438_slice_xy.png` | Particle3D regression, 10,000,000 particles, 438 steps. |
| `particle3d_reference_slice_xy.png` | Reference-model plot for the same Particle3D regression. |
| `wave_restore_density.png` | Wave restore demo, restored hardware output. |
| `wave_restore_real.png` | Wave restore demo, restored real-field output. |

## Suggested Video Flow

Use [`VIDEO_STORYBOARD.md`](VIDEO_STORYBOARD.md) as the script outline.

1. FLX1.0 runs a deterministic hardware workload.
2. A reference-model run is produced for the same workload.
3. Hardware and reference outputs are compared.
4. Restore/recovery is demonstrated.
5. The final report shows zero mismatches for the validated cases.

## Authenticity Notes

- The plot images are copied from the generated acceptance evidence, not drawn as marketing illustrations.
- The validation card is generated from the acceptance manifest and summary status.
- The media manifest records SHA-256 hashes for the presentation files.
- The full technical evidence archive is `../evidence/acceptance_20260606_full`.
