# Urban greenspace drivers of bird species richness differ between migratory and resident species across the full-annual cycle

This repository contains all code and derived data necessary to reproduce the analyses, figures, and tables for the manuscript published in Ornithological Applications:

> **“Urban greenspace drivers of bird species richness differ between migratory and resident species across the full-annual cycle.”**

The project quantifies seasonal patterns of avian species richness across urban greenspaces and contrasts responses between migratory and resident species using eBird data, greenspace attributes, and human modification metrics.

------------------------------------------------------------------------

## Getting started

The simplest way to reproduce the full workflow is to open the project’s `.Rproj` file and run the scripts in order.

**Recommended execution order**

1.  Run scripts **1–7** in the `R/` directory sequentially for the main analyses presented in the paper.

2.  Run scripts **2_1–7_1** in the `R/` directory sequentially for the supplementary sensitivity analysis that produces Supplementary Material Figure S2 *(these files repeat the main analysis files **2-7** but retain checklists with X observations included)*.

3.  Run the scripts titled 'misc' last which produces figure 1, additional supplementary figures and tables, and explores the data further.

All analyses were conducted in **R**, and required packages are loaded within individual scripts.

------------------------------------------------------------------------

## Repository structure

### `R/`

Scripts for data processing, modeling, and figure/table generation.

- **Scripts 1–4**:
  - Filter and process eBird data
  - Spatially overlay observations with greenspaces
  - Select urban greenspaces
  - Derive greenspace attributes (area, isolation, and GHMI)
- **Scripts 5–7**:
  - Fit species richness models
  - Generate **Figures 2–5**
  - Generate **Supplementary Tables S2A–S2E**
- **Scripts 2_1–7_1**:
  - Repeats the analysis from scripts 1–7, but retains checklists with X observations included
  - Generate **Supplementary Material Figure S2**
- **Miscellaneous scripts** (`R/misc/`):
  - Create **Figure 1**
  - Create **Supplementary Figures**
  - Create **Supplementary Tables**

**Important notes**: - Script **1** relies on raw data files that are too large to be hosted on GitHub. These files are available upon request (via email). Users without access to these files can begin inspection and execution at **Script 2**. GHMI data extraction requires access to **Google Earth Engine**.

------------------------------------------------------------------------

### `data/`

Input and intermediate datasets used throughout the workflow.

- **`AVONET/`**
  - AVONET trait data
  - RDS files with assigned migratory status
- **`eBird/`**
  - Raw data is too large to be hosted on GitHub, but if obtained should be saved to this folder
  - Processed eBird data
  - Extracted eBird files used in analyses
- **`ghmi_dynamic_world/`**
  - CSV containing mean GHMI values per park
  - Used to append GHMI metrics to the final dataset
- **`intermediate_data/`**
  - Saved intermediate objects produced from R scripts used to reduce runtime
  - Many long-running sections of scripts are commented out (`###`) and replaced by loading these files
- **`polygons/`**
  - Shapefiles for South Florida study area and greenspaces
- **`final_data_for_big_script.RDS`**
  - Final compiled dataset used for all models
  - Loaded as `greenspaces` in modeling scripts

------------------------------------------------------------------------

### `figures/`

Contains all figures and tables included in the manuscript.

- Files are saved as `.png` or `.pdf`
- Organized into subfolders by **figure or table number**
- Includes all main-text figures and supplementary materials

The location of the main figures are as follows: Figure 1 (Fig_1), Figure 2 (effect_size), Figure 3 (area), Figure 4 (isolation), and Figure 5 (gmhi).
