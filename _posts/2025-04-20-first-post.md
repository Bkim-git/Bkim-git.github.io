---
layout: default
title: "DfW Algorithm – Release Notes"
---

## Release Notes


### 24 March 2025 – [DfW v1.1](https://doi.org/10.5281/zenodo.15861158)
- **Input Video Format Update**  
  The required input video format has been updated from a compressed NumPy archive (`*.npz`) to standard video formats such as `*.mov` or `*.mp4`, improving compatibility and usability.

- **Coordinate System Handling**  
  Previously, local spatial coordinates (`xi`, `yi`) were embedded within the `.npz` file as 2D arrays matching the video resolution. In the updated version, spatial referencing is now provided via a separate `extent.txt` file, formatted as:  
  `xmin xmax ymin ymax`.

- **Configuration Management**  
  Required parameters are no longer hardcoded in `init.py`. All runtime configurations are now specified in a standalone `config.yaml` file, improving modularity, version control, and transparency.

- **Visualization Enhancement**  
  Results can now be overlaid on satellite imagery using an optional `basemap.png` file, allowing for improved geospatial interpretability of the outputs.

- **Ground Truth Input Flexibility**  
  Ground truth data can now be provided in multiple formats:
  - **Raster-based**: e.g., GeoTIFF for gridded reference surfaces.
  - **Point-based**: e.g., `*.csv` or `*.xyz` for point cloud data.

### 24 March 2025 – [DfW v1.0](https://doi.org/10.5281/zenodo.15075314)
- Initial release of the DfW algorithm.
