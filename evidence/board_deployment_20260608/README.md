# FLX Board Deployment Evidence - 8 June 2026

Build/programming/deployment proof for the 8 June board run.

Key files:

- `build_100t_result_accum_fix_20260608_125049.log` - Vivado 100T build/timing/MCS log.
- `program_100t_cfgmem_result_accum_fix_retry_20260608.log` - Arty A7-100T config-memory programming log.
- `program_cmod_35t_cfgmem_20260608.log` - Cmod A7-35T config-memory programming log.
- `board_acceptance_20260608_135515.stdout.log` - streamed board acceptance output.
- `board_acceptance_summary.json` - wrapper summary for the board acceptance run.
- `file_hashes_sha256.txt` - integrity hashes for this evidence folder.

Result: 100T timing closed (`ROUTED_WNS=0.134`), both FPGA config memories verified, Z7 acceptance passed.
