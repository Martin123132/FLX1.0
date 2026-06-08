# GMW Wave Restore Demo

- final_pass: `True`
- shape: `[4, 4, 1]`
- timesteps: `32`
- center_index: `10`
- kernel_contract: `a7_mts_full_physics_kernel_v2_q16`
- kernel_contract_word: `0x4D545332`

## Comparisons

- CPU vs baseline FPGA: `True`
- CPU vs restored FPGA: `True`
- baseline FPGA vs restored FPGA: `True`

## Outputs

- `uart_wave_restore.log`
- `cpu_reference/field.csv`
- `fpga_baseline/field.csv`
- `fpga_restored/field.csv`
- `fpga_restored/mts_report.md`
