# FLX Adaptability Workload Suite

- Port: `COM5`
- Baud: `115200`
- Final pass: `True`

| Case | Class | CPU rate | FLX kernel rate | FLX/CPU kernel ratio | Expected | FLX | Pass |
|---|---|---:|---:|---:|---:|---:|---:|
| vm_load_xor_bitwork | normal_cpu_integer_bitwork | 1666669.134 | 5882352.941 | 3.529 | 0xB791F3DD | 0xB791F3DD | True |
| vm_q16_multiply_load | fixed_point_q16_arithmetic | 2857135.950 | 5405405.405 | 1.892 | 0xFFFFA000 | 0xFFFFA000 | True |
| vm_rotr_bit_permutation | normal_cpu_integer_bitwork | 1999999.323 | 3030303.030 | 1.515 | 0x78123456 | 0x78123456 | True |
| vm_filter_count_reduce | database_filter_count | 8888893.066 | 23529411.765 | 2.647 | 0x00000004 | 0x00000004 | True |
| vm_checksum_xor_reduce | normal_cpu_integer_bitwork | 10000014.805 | 15384615.385 | 1.538 | 0x6633423D | 0x6633423D | True |
| vm_signed_min_reduce | normal_cpu_scan_reduction | 13333231.808 | 15384615.385 | 1.154 | 0xFFFFFFEC | 0xFFFFFFEC | True |
| vm_signed_max_reduce | normal_cpu_scan_reduction | 10000014.805 | 15384615.385 | 1.538 | 0x00000005 | 0x00000005 | True |
| vm_lattice_neighbor_index | lattice_addressing_helper | 106666501.206 | 228571428.571 | 2.143 | 0x0000000B | 0x0000000B | True |
| sand_fall_local_rules | world_state_local_rules | 2122719.750 | 15993336.110 | 7.534 | 0x0534C9FA | 0x0534C9FA | True |
| factory_conveyor_jam | world_state_local_rules | 3427959.275 | 16256032.512 | 4.742 | 0x5C4FA6A5 | 0x5C4FA6A5 | True |
| swarm_wrap_edges | world_state_local_rules | 3832335.321 | 16211652.125 | 4.230 | 0x894C99C6 | 0x894C99C6 | True |

## What This Adds

These are additional live hardware workload cases beyond the prior SHA, MTS field, Particle3D, and WAL recovery evidence. Some classes were discussed earlier; this suite records fresh CPU-reference-vs-FLX runs for them instead of treating discussion as proof.

New live CPU-style cases added here include database/filter count reduction, XOR checksum reduction, signed min/max scan reduction, and lattice-neighbour addressing.

The world-grid cases run through the same FLX hardware helper with different deterministic data/configuration, not through separate one-off demos.
