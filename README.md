# Halide_Turorial
This repository will introduce the basic of Halide -> (Algorithm + Scheduling)

## Basic Functions

Tile             |   Tile + Fuse + Parallel | Vectorize (SIMD) |  Unroll Loop
:-------------------------:|:-------------------------: |:-------------------------: |:-------------------------:
Divide whole image into tiles|  Taling parallel |   x86 SSE command |  Reduce repeat calculation
![](./figures/tile.gif?raw=true)  | ![](./figures/tile_parallel.gif?raw=true) | ![](./figures/vectorize.gif?raw=true) |  ![](./figures/unroll.gif?raw=true)


## Scheduling multi-stage pipelines

producer(x, y) = sin(x * y)

consumer(x, y) = (producer(x, y) +
                  producer(x, y+1) +
                  producer(x+1, y) +
                  producer(x+1, y+1))/4




 store_root.compute_at |  Tiling + compute_at
:-------------------------: |:-------------------------:
 Store intermediate data in several scanlines |  Divide compute_at into tiles
![](./figures/root_at.gif?raw=true) |  ![](./figures/tile_at.gif?raw=true)


compute_root             |   compute_at 
:-------------------------:|:-------------------------: 
Compute all producer before use|  Compute producer inside y loop 
![](./figures/compute_root.gif?raw=true)  | ![](./figures/compute_at.gif?raw=true) 









  
