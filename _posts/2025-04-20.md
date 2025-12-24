---
layout: default
title: "DfW Algorithm – Release Notes"
---

## Release Notes

### 24 December 2025 – DfW v2.0

- **Parallelization Redesign**  
  The depth inversion workflow has been fundamentally restructured to support true process-level parallelism.  
  Mode-wise and point-wise depth estimation are now executed in parallel using `joblib`, enabling efficient scaling on multi-core systems.

- **Shared-Memory–Based Data Exchange**  
  Large intermediate arrays (Dynamic Modes and corresponding masks) are no longer copied to each worker process.  
  Instead, they are placed in shared memory and accessed read-only by parallel workers, significantly reducing memory overhead and inter-process communication cost.

- **Deterministic Performance via Thread Control**  
  To avoid nested parallelism and performance instability, BLAS and MKL internal threading are explicitly disabled (single-threaded execution), ensuring reproducible runtime behavior when combined with process-based parallelism.

- **Parallel-Safe Refactoring of Core Routines**  
  Core routines in `modules` have been refactored to be stateless and shared-memory–friendly, enabling safe parallel execution without side effects or race conditions.

### 11 Julu 2025 – [DfW v1.1](https://doi.org/10.5281/zenodo.15861158)
- **Input Video Format Update**  
  The required input video format has been updated from a compressed NumPy archive (`*.npz`) to standard video formats such as `*.mov` or `*.mp4`.

- **Coordinate System Handling**  
  Previously, local spatial coordinates (`xi`, `yi`) were embedded within the `.npz` file as 2D arrays matching the video resolution. In the updated version, spatial referencing is now provided via a separate `extent.txt` file, formatted as: [`xmin xmax ymin ymax`].

- **Configuration Management**  
  Required parameters are no longer hardcoded in `init.py`. All runtime configurations are now specified in a standalone `config.yaml` file.

- **Visualization Enhancement**  
  Results can now be overlaid on satellite imagery using an optional `basemap.png` file.

- **Ground Truth Input Flexibility**  
  Ground truth data can now be provided in multiple formats:
  - **Raster-based**: e.g., GeoTIFF for gridded reference surfaces.
  - **Point-based**: e.g., `*.csv` or `*.xyz` for point cloud data.

### 24 March 2025 – [DfW v1.0](https://doi.org/10.5281/zenodo.15075314)
- Initial release of the DfW algorithm.
