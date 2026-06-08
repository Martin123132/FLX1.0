# Flash-Booted Post-RTL Adaptability Evidence

Date: **8 June 2026**

Result: **PASS**

This evidence folder records the completed non-volatile deployment proof for the post-RTL A7-100T image:

1. The A7-100T design was rebuilt from current RTL.
2. Vivado implementation timing passed.
3. `config_100t.mcs` was generated.
4. The MCS was programmed into A7-100T configuration flash.
5. Vivado verified the flash programming operation.
6. The FPGA was booted from programmed configuration memory.
7. The COM5 hardware adaptability suite passed after that flash boot.

## Deployment Gate

| Gate | Result |
|---|---:|
| A7-100T synthesis | Pass |
| A7-100T implementation | Pass |
| Routed timing | `WNS=0.239 ns`, `TNS=0` |
| Bitstream generated | Pass |
| `config_100t.mcs` generated | Pass |
| Config flash erase | Pass |
| Config flash program/verify | Pass |
| Boot from programmed configuration memory | Done pin HIGH |
| Post-flash-boot COM5 test | Pass |

Key flash log lines:

- `Program/Verify Operation successful.`
- `Flash programming completed successfully`
- `Booting FPGA from programmed configuration memory`
- `Done pin status: HIGH`

## Workloads Tested After Flash Boot

| Case | Workload Class | CPU Expected | FLX Result | Result |
|---|---|---:|---:|---:|
| `vm_load_xor_bitwork` | normal CPU integer bitwork | `0xB791F3DD` | `0xB791F3DD` | Pass |
| `vm_q16_multiply_load` | fixed-point Q16 arithmetic | `0xFFFFA000` | `0xFFFFA000` | Pass |
| `vm_rotr_bit_permutation` | normal CPU integer bitwork | `0x78123456` | `0x78123456` | Pass |
| `vm_filter_count_reduce` | database/filter count | `0x00000004` | `0x00000004` | Pass |
| `vm_checksum_xor_reduce` | checksum/integer reduction | `0x6633423D` | `0x6633423D` | Pass |
| `vm_signed_min_reduce` | signed scan reduction | `0xFFFFFFEC` | `0xFFFFFFEC` | Pass |
| `vm_signed_max_reduce` | signed scan reduction | `0x00000005` | `0x00000005` | Pass |
| `vm_lattice_neighbor_index` | lattice addressing helper | `0x0000000B` | `0x0000000B` | Pass |
| `sand_fall_local_rules` | world-state local rules | `0x0534C9FA` | `0x0534C9FA` | Pass |
| `factory_conveyor_jam` | world-state local rules | `0x5C4FA6A5` | `0x5C4FA6A5` | Pass |
| `swarm_wrap_edges` | world-state local rules | `0x894C99C6` | `0x894C99C6` | Pass |

## Source Artefacts

- [build_100t_validate_current_source.log](build_100t_validate_current_source.log)
- [program_100t_post_rtl_flash_20260608.log](program_100t_post_rtl_flash_20260608.log)
- [adaptability_summary.json](adaptability_summary.json)
- [adaptability_benchmark.csv](adaptability_benchmark.csv)
- [adaptability_report.md](adaptability_report.md)
- [uart_adaptability.log](uart_adaptability.log)
- [file_hashes_sha256.txt](file_hashes_sha256.txt)

Visual panel:

- [../../MEDIA/evidence_panels/adaptability_flash_boot_panel.png](../../MEDIA/evidence_panels/adaptability_flash_boot_panel.png)
