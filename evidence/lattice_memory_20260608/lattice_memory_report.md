# FLX Lattice Memory Acceptance

Final pass: `True`

## What This Proves

- Logical 1D, 2D, and 3D coordinates map into dense local addresses under row, snake, and Morton layouts.
- Every active point has exactly one local address and every local address is reachable.
- Coordinate -> local index -> coordinate round trips are deterministic.
- Wrapped neighbour references stay inside the active lattice for all checked points.
- The live Z7/A7 `layout-map` command agrees with the host mapper for boundary and centre coordinates.

## Host Exhaustive Coverage

- Cases: `48/48`
- Shapes include 1D up to 1024, 2D up to 32x32, and 3D up to 10x10x10.
- Each case checks dense local addressing, inverse mapping, round-trip logical coordinates, and neighbours.

## Live Board Cross-Check

- Port: `COM5` at `115200` baud
- Cases: `51/51`
- Pass: `True`
- Uses live `layout-status`, `layout-set`, `layout-map`, `route-status`, and `route-read 0 0` commands.

## Visual Memory Maps

These panels show how the same logical lattice is packed by row-major, snake/serpentine, and Morton/Z-order layouts.

![2D 32x32 layout map](E:/GMW_CPU/results/lattice_memory/board_crosscheck_final_20260608/layout_2d_32x32_row_snake_morton.png)

![3D 8x8x8 layout map](E:/GMW_CPU/results/lattice_memory/board_crosscheck_final_20260608/layout_3d_8x8x8_row_snake_morton.png)

![3D 10x10x10 layout map](E:/GMW_CPU/results/lattice_memory/board_crosscheck_final_20260608/layout_3d_10x10x10_row_snake_morton.png)

## Order CSVs

- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\morton_1d_1024x1x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\morton_2d_32x32x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\morton_3d_8x8x8_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\morton_3d_10x10x10_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\row_1d_1024x1x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\row_2d_32x32x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\row_3d_8x8x8_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\row_3d_10x10x10_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\snake_1d_1024x1x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\snake_2d_32x32x1_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\snake_3d_8x8x8_order.csv`
- `E:\GMW_CPU\results\lattice_memory\board_crosscheck_final_20260608\snake_3d_10x10x10_order.csv`

## Host Cases

| layout | dim | shape | points | dense | roundtrip | neighbours | pass |
|---|---:|---|---:|---|---|---:|---|
| morton | 1 | 1x1x1 | 1 | True | True | 2 | True |
| morton | 1 | 7x1x1 | 7 | True | True | 14 | True |
| morton | 1 | 64x1x1 | 64 | True | True | 128 | True |
| morton | 1 | 100x1x1 | 100 | True | True | 200 | True |
| morton | 1 | 256x1x1 | 256 | True | True | 512 | True |
| morton | 1 | 512x1x1 | 512 | True | True | 1024 | True |
| morton | 1 | 1024x1x1 | 1024 | True | True | 2048 | True |
| morton | 2 | 1x1x1 | 1 | True | True | 4 | True |
| morton | 2 | 4x4x1 | 16 | True | True | 64 | True |
| morton | 2 | 8x16x1 | 128 | True | True | 512 | True |
| morton | 2 | 16x16x1 | 256 | True | True | 1024 | True |
| morton | 2 | 32x32x1 | 1024 | True | True | 4096 | True |
| morton | 3 | 1x1x1 | 1 | True | True | 6 | True |
| morton | 3 | 4x4x4 | 64 | True | True | 384 | True |
| morton | 3 | 8x8x8 | 512 | True | True | 3072 | True |
| morton | 3 | 10x10x10 | 1000 | True | True | 6000 | True |
| row | 1 | 1x1x1 | 1 | True | True | 2 | True |
| row | 1 | 7x1x1 | 7 | True | True | 14 | True |
| row | 1 | 64x1x1 | 64 | True | True | 128 | True |
| row | 1 | 100x1x1 | 100 | True | True | 200 | True |
| row | 1 | 256x1x1 | 256 | True | True | 512 | True |
| row | 1 | 512x1x1 | 512 | True | True | 1024 | True |
| row | 1 | 1024x1x1 | 1024 | True | True | 2048 | True |
| row | 2 | 1x1x1 | 1 | True | True | 4 | True |
| row | 2 | 4x4x1 | 16 | True | True | 64 | True |
| row | 2 | 8x16x1 | 128 | True | True | 512 | True |
| row | 2 | 16x16x1 | 256 | True | True | 1024 | True |
| row | 2 | 32x32x1 | 1024 | True | True | 4096 | True |
| row | 3 | 1x1x1 | 1 | True | True | 6 | True |
| row | 3 | 4x4x4 | 64 | True | True | 384 | True |
| row | 3 | 8x8x8 | 512 | True | True | 3072 | True |
| row | 3 | 10x10x10 | 1000 | True | True | 6000 | True |
| snake | 1 | 1x1x1 | 1 | True | True | 2 | True |
| snake | 1 | 7x1x1 | 7 | True | True | 14 | True |
| snake | 1 | 64x1x1 | 64 | True | True | 128 | True |
| snake | 1 | 100x1x1 | 100 | True | True | 200 | True |
| snake | 1 | 256x1x1 | 256 | True | True | 512 | True |
| snake | 1 | 512x1x1 | 512 | True | True | 1024 | True |
| snake | 1 | 1024x1x1 | 1024 | True | True | 2048 | True |
| snake | 2 | 1x1x1 | 1 | True | True | 4 | True |
| snake | 2 | 4x4x1 | 16 | True | True | 64 | True |
| snake | 2 | 8x16x1 | 128 | True | True | 512 | True |
| snake | 2 | 16x16x1 | 256 | True | True | 1024 | True |
| snake | 2 | 32x32x1 | 1024 | True | True | 4096 | True |
| snake | 3 | 1x1x1 | 1 | True | True | 6 | True |
| snake | 3 | 4x4x4 | 64 | True | True | 384 | True |
| snake | 3 | 8x8x8 | 512 | True | True | 3072 | True |
| snake | 3 | 10x10x10 | 1000 | True | True | 6000 | True |
