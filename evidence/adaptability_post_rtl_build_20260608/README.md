# Superseded Post-RTL-Build Adaptability Evidence

Date: **8 June 2026**

Result: **PASS**

This folder is retained only as the earlier JTAG-loaded comparison run. The current non-volatile proof is:

- [../adaptability_flash_boot_20260608/README.md](../adaptability_flash_boot_20260608/README.md)

That newer folder records the same current-source A7-100T path after `config_100t.mcs` was programmed and verified in configuration flash, booted from programmed configuration memory, and tested over COM5.

This older folder records a live COM5 hardware run after rebuilding the Arty A7-100T design from the current RTL source and programming the generated bitstream over JTAG.

## Build Gate

| Gate | Result |
|---|---:|
| A7-100T synthesis | Pass |
| A7-100T implementation | Pass |
| Routed timing | `WNS=0.239 ns`, `TNS=0` |
| Bitstream generated | Pass |
| `config_100t.mcs` generated | Pass |
| JTAG bitstream program for live test | Pass |
| Config-flash program/verify | Superseded by flash-boot evidence |

The post-build live test below was run before the later config-flash proof. Use [../adaptability_flash_boot_20260608/README.md](../adaptability_flash_boot_20260608/README.md) for the current non-volatile evidence.

## Workloads Tested

| Case | Workload Class | CPU Expected | FLX Result | Kernel Ratio | Result |
|---|---|---:|---:|---:|---:|
| `vm_load_xor_bitwork` | normal CPU integer bitwork | `0xB791F3DD` | `0xB791F3DD` | `3.529x` | Pass |
| `vm_q16_multiply_load` | fixed-point Q16 arithmetic | `0xFFFFA000` | `0xFFFFA000` | `1.892x` | Pass |
| `vm_rotr_bit_permutation` | normal CPU integer bitwork | `0x78123456` | `0x78123456` | `1.515x` | Pass |
| `vm_filter_count_reduce` | database/filter count | `0x00000004` | `0x00000004` | `2.647x` | Pass |
| `vm_checksum_xor_reduce` | checksum/integer reduction | `0x6633423D` | `0x6633423D` | `1.538x` | Pass |
| `vm_signed_min_reduce` | signed scan reduction | `0xFFFFFFEC` | `0xFFFFFFEC` | `1.154x` | Pass |
| `vm_signed_max_reduce` | signed scan reduction | `0x00000005` | `0x00000005` | `1.538x` | Pass |
| `vm_lattice_neighbor_index` | lattice addressing helper | `0x0000000B` | `0x0000000B` | `2.143x` | Pass |
| `sand_fall_local_rules` | world-state local rules | `0x0534C9FA` | `0x0534C9FA` | `7.534x` | Pass |
| `factory_conveyor_jam` | world-state local rules | `0x5C4FA6A5` | `0x5C4FA6A5` | `4.742x` | Pass |
| `swarm_wrap_edges` | world-state local rules | `0x894C99C6` | `0x894C99C6` | `4.230x` | Pass |

## Why This Set Matters

This run adds workload diversity beyond the existing SHA/MTS/Particle3D/WAL evidence. It proves the programmable VM path can execute direct RAM loads, integer bit operations, Q16 fixed-point arithmetic, reductions, and lattice neighbour addressing against CPU/reference results. It also includes three different world-state local-rule cases using the existing world-grid accelerator path.

## Source Artefacts

- [adaptability_summary.json](adaptability_summary.json)
- [adaptability_benchmark.csv](adaptability_benchmark.csv)
- [adaptability_report.md](adaptability_report.md)
- [uart_adaptability.log](uart_adaptability.log)
- [file_hashes_sha256.txt](file_hashes_sha256.txt)

Visual panel:

- [../../MEDIA/evidence_panels/adaptability_post_rtl_build_panel.png](../../MEDIA/evidence_panels/adaptability_post_rtl_build_panel.png)
