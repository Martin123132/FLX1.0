# FLX1.0 3D Generality Evidence

This folder contains dense 3D hardware/reference evidence copied into a presentation-safe evidence layout.

Each case includes:

- `hardware_field.csv`: final field read from hardware.
- `reference_field.csv`: matching fixed-point reference field.
- `density_error.csv`: per-site density difference between reference and hardware.
- `compare_report.json`: cleaned compare metrics for this public evidence repo.

## Cases

| Case | Shape | Active points | Result |
| --- | --- | ---: | --- |
| delta_field | [8, 8, 8] | 512 | PASS, mismatches=0, max_abs_delta_q16=0 |
| gaussian_field | [8, 8, 8] | 512 | PASS, mismatches=0, max_abs_delta_q16=0 |
| plane_wave_field | [8, 8, 8] | 512 | PASS, mismatches=0, max_abs_delta_q16=0 |
| random_field | [8, 8, 8] | 512 | PASS, mismatches=0, max_abs_delta_q16=0 |


These cases are used by the media panels named `flx3d_generality_*_panel.png`.
