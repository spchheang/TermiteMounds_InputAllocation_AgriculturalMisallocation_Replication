# Replication Code for the Paper  
# *Termite Mounds, Input Allocation, and Agricultural Misallocation*

## Author

**Sreyphea Chheang**  
Postdoctoral Fellow, CERDI, Université Clermont Auvergne  
Ph.D. in Economics, York University (2025)  

GitHub: <https://github.com/spchheang>

---

## Overview

This repository contains the replication code for the paper *Termite Mounds, Input Allocation, and Agricultural Misallocation*. The project studies agricultural misallocation in rice production in the Chrey Bak catchment, Kampong Chhnang Province, Cambodia.

The replication files use **Python** and **Stata** to prepare geographic and climate variables, clean and merge plot-level survey data, estimate production-function parameters, construct plot-level productivity measures, calculate efficiency gains from input reallocation, decompose misallocation into within-type and between-type components, and produce tables and figures for the paper.

The analysis focuses on two related but distinct margins:

1. **Termite-mound presence**, which captures ecological heterogeneity across plots.
2. **Termite-mound soil use**, which captures farmers' use of termite-mound soil as a soil amendment.

The main objective is to examine whether land and labor are efficiently allocated across plots that differ in productivity and ecological characteristics, and to quantify potential output gains from reallocating inputs according to an efficient benchmark.

---

## Research Background

The paper studies agricultural misallocation in a setting where productivity heterogeneity is partly observable and linked to ecological variation from termite mounds. Termite mounds can affect soil characteristics such as nutrient content, organic matter, and water retention. These ecological differences may generate systematic variation in plot-level productivity.

Using plot-level panel data from rice farmers in Cambodia, the paper estimates productivity from a production function and compares the observed allocation of land and labor with an efficient allocation implied by a planner's benchmark. The empirical framework also corrects productivity measures for measurement error and transitory shocks.

The paper distinguishes between misallocation across ecological types and misallocation within ecological types. This distinction helps identify whether output losses arise mainly from the allocation of inputs between termite-mound and non-termite-mound plots, or from inefficient input allocation among plots of the same type.

---

## Main Findings

The paper finds substantial inefficiencies in the allocation of land and labor across rice plots. After adjusting for measurement error and transitory shocks, reallocating inputs according to the efficient benchmark would increase aggregate rice output by approximately 45 percent at the Chrey Bak catchment level.

Most of these gains arise from **within-type reallocation**, rather than from **between-type reallocation**. This means that the main source of inefficiency is not simply the allocation of inputs between termite-mound and non-termite-mound plots. Instead, most efficiency losses arise because inputs are not efficiently allocated among plots with similar ecological characteristics.

The paper also highlights an additional margin of inefficiency related to the limited use of termite-mound soil amendment. Even though termite-mound soil can increase rice yields, its use remains limited among plots with access to termite mounds. This suggests that productivity losses arise not only from the misallocation of conventional inputs such as land and labor, but also from the underuse of locally available productivity-enhancing inputs.

---

## Significance

This project contributes to the literature on agricultural productivity and misallocation in developing economies. It shows that ecological heterogeneity can provide an observable source of productivity differences across plots and that local distortions in input allocation can generate large output losses.

The findings suggest that improving agricultural productivity requires more than reallocating conventional inputs across broad plot types. Policies may also need to address barriers to efficient input use within local areas and encourage the adoption of locally available productivity-enhancing inputs, such as termite-mound soil amendment.

---

## Data Sources Used in This Paper

### 1. Plot-Level Survey Data

The main dataset comes from plot-level surveys of rice farmers in Kampong Chhnang Province, Cambodia, covering the 2021-2023 rice-growing seasons. The survey focuses on villages located in and around the Chrey Bak catchment.

The data include information on:

- Rice output
- Land input
- Labor input
- Seed, fertilizer, and pesticide use
- Termite-mound presence
- Termite-mound soil use
- Household characteristics
- Plot characteristics
- Village, commune, district, season, and year identifiers

The data distinguish between plots with termite mounds and plots where farmers use termite-mound soil as an amendment.

### 2. Geographic and Climate Data

The replication files also construct village-level geographic and climate characteristics using Python. These variables are used as additional controls in the empirical analysis.

The geographic and climate data include:

- Soil texture and soil properties from SoilGrids
- Elevation and terrain characteristics
- Climate variables from WorldClim
- Waterway and distance-to-water measures
- Village coordinates and administrative boundaries
- Chrey Bak catchment boundary data

These variables are merged with the plot-level survey data and used in robustness checks.

---

## Software Requirements

The replication code uses both Python and Stata.

### Python

Python is used mainly to prepare geographic and climate variables. The required Python packages include:

- `pandas`
- `geopandas`
- `matplotlib`
- `rasterio`
- `numpy`
- `rasterstats`
- `pathlib`
- `os`

These packages are loaded in the setup notebook:

```text
0_Setup.ipynb
```

### Stata

Stata is used for data cleaning, estimation, productivity construction, efficiency calculations, decomposition of misallocation, robustness checks, and table generation.

The main Stata script is:

```text
0_master.do
```

---

## Repository Structure

A suggested structure for the repository is:

```text
.
├── README.md
├── Python/
│   ├── 0_Setup.ipynb
│   └── other Python notebooks for geographic and climate variables
├── StataFile/
│   ├── 0_master.do
│   ├── 4_Cleaned_Merged_Data.do
│   ├── 5_1_Cal_betaL_betaN.do
│   ├── 6_2_TFP_VC_Con_Winsorize_FullSample.do
│   ├── 6_2_1_TFP_VC_Con_Winsorize_FullSample_Type.do
│   ├── 6_3_Test_mean_TFP.do
│   ├── 6_4_Stats_Tab.do
│   ├── 6_5_TFP_VC_Con_Winsorize_FullSample_IVCRE.do
│   ├── 7_1_Cal_Efficiency.do
│   ├── 7_2_Cal_Share_Efficiency.do
│   ├── 7_3_Cal_Share_Efficiency_ByGroup.do
│   ├── 7_4_Cal_Efficiency_HH.do
│   ├── 7_5_Cal_Share_Efficiency_HH.do
│   ├── 7_6_Cal_Share_Efficiency_ByGroup_HH.do
│   ├── 7_7_Cal_Efficiency_IVCRE.do
│   ├── 8_1_Cal_Efficiency_MOD.do
│   ├── 8_2_Cal_Share_Efficiency_MOD.do
│   ├── 8_3_Cal_Share_Efficiency_ByGroup_MOD.do
│   ├── 8_4_Cal_betaL_betaN_MOD.do
│   └── 8_5_TFP_VC_Con_Winsorize_FullSample_MOD.do
├── RawData/
├── Data/
├── Figure/
└── Table/
```

---

## Python Workflow

Python is used to construct geographic and climate variables at the village level. The setup notebook defines common file paths, loads required packages, and identifies the input and output files used in the geographic-data workflow.

The Python scripts prepare or use the following files:

```text
CB_District.kml
TM_Village.csv
TM_Village_with_geo_climate_1km.csv
TM_Village_with_geo_climate_1km_waterdist.csv
```

The Python workflow is used to:

1. Load administrative boundary files and the Chrey Bak catchment boundary.
2. Load village coordinates from `TM_Village.csv`.
3. Extract soil, terrain, climate, and water-access variables.
4. Calculate village-level geographic characteristics.
5. Export processed village-level geographic and climate variables for use in Stata.

---

## Stata Workflow

The Stata workflow is controlled by:

```text
0_master.do
```

The master script sets the project directory, defines paths for raw data, cleaned data, figures, and tables, and then runs the main Stata scripts sequentially.

### Main Stata Steps

The Stata workflow performs the following steps:

1. Clean and merge the plot-level survey data.
2. Estimate production-function parameters for land and labor.
3. Construct plot-level total factor productivity.
4. Adjust productivity to reduce the influence of measurement error and transitory shocks.
5. Test productivity differences across termite-mound and non-termite-mound plot types.
6. Generate summary statistics.
7. Calculate efficiency gains from reallocating land and labor.
8. Decompose total efficiency gains into between-type and within-type components.
9. Calculate the contribution of termite-mound and non-termite-mound plots to total gains.
10. Repeat the analysis at the farm level.
11. Run robustness checks using additional household and geographic controls.
12. Export tables in LaTeX format.

---

## Main Stata Scripts

The main Stata files include:

```text
4_Cleaned_Merged_Data.do
```

Cleans and merges the main plot-level survey data with geographic and climate variables.

```text
5_1_Cal_betaL_betaN.do
```

Estimates production-function parameters for land and labor.

```text
6_2_TFP_VC_Con_Winsorize_FullSample.do
```

Constructs plot-level productivity measures and applies correction for measurement error and transitory shocks.

```text
6_2_1_TFP_VC_Con_Winsorize_FullSample_Type.do
```

Constructs productivity measures by ecological type.

```text
6_3_Test_mean_TFP.do
```

Tests productivity differences across plot types.

```text
6_4_Stats_Tab.do
```

Produces summary-statistics tables.

```text
6_5_TFP_VC_Con_Winsorize_FullSample_IVCRE.do
```

Constructs productivity measures using the IV-CRE specification.

```text
7_1_Cal_Efficiency.do
```

Calculates total efficiency gains from reallocating inputs according to the efficient benchmark.

```text
7_2_Cal_Share_Efficiency.do
```

Decomposes aggregate efficiency gains into within-type and between-type components.

```text
7_3_Cal_Share_Efficiency_ByGroup.do
```

Calculates the contribution of each plot type to total efficiency gains.

```text
7_4_Cal_Efficiency_HH.do
```

Calculates efficiency gains at the farm or household level.

```text
7_5_Cal_Share_Efficiency_HH.do
```

Decomposes farm-level efficiency gains.

```text
7_6_Cal_Share_Efficiency_ByGroup_HH.do
```

Calculates the contribution of each plot type to farm-level efficiency gains.

```text
7_7_Cal_Efficiency_IVCRE.do
```

Calculates efficiency gains using the IV-CRE productivity specification.

```text
8_1_Cal_Efficiency_MOD.do
8_2_Cal_Share_Efficiency_MOD.do
8_3_Cal_Share_Efficiency_ByGroup_MOD.do
8_4_Cal_betaL_betaN_MOD.do
8_5_TFP_VC_Con_Winsorize_FullSample_MOD.do
```

Run robustness checks using additional household and geographic controls.

---

## Outputs

The code produces the following outputs:

- Cleaned analysis datasets
- Village-level geographic and climate variables
- Estimated production-function parameters
- Plot-level productivity measures
- Adjusted productivity measures
- Efficiency-gain estimates
- Within-type and between-type decomposition results
- Farm-level efficiency results
- Robustness-check results
- Summary-statistics tables
- LaTeX tables
- Figures used in the paper

Outputs are saved in the project folders defined in `0_master.do`, including:

```text
Data/
Figure/
Table/
```

---

## How to Run the Replication Code

### Step 1: Set the Project Directory

Before running the code, edit the project paths in both the Python setup notebook and the Stata master file.

In Python, update the base directory in:

```text
0_Setup.ipynb
```

In Stata, update the path in:

```stata
global PATH "/your/project/path"
```

inside:

```text
0_master.do
```

### Step 2: Run the Python Files

Run the Python notebooks first to construct geographic and climate variables at the village level.

The main setup file is:

```text
0_Setup.ipynb
```

This file loads the required packages and defines the paths used in the geographic-data workflow.

### Step 3: Run the Stata Master File

After preparing the geographic and climate variables, run:

```text
0_master.do
```

This file executes the main data-cleaning, estimation, productivity, misallocation, decomposition, and robustness-check routines.

### Step 4: Check Output Folders

After the scripts finish running, check the following folders:

```text
Data/
Figure/
Table/
```

These folders contain the cleaned data, figures, and LaTeX tables generated by the replication code.

---

## Notes

- Some raw datasets may not be included in this repository because of data-use restrictions.
- Users should place all required raw data files in the `RawData/` folder before running the code.
- The code assumes that the folder structure follows the paths defined in `0_master.do` and `0_Setup.ipynb`.
- The Python files should be run before the Stata replication files if geographic and climate variables need to be reconstructed.
- The Stata master file can be modified to run only selected parts of the analysis.

---

## Citation

If you use this replication package, please cite:

Chheang, Sreyphea. *Termite Mounds, Input Allocation, and Agricultural Misallocation*. Working paper.

---

## Contact

For questions about the replication code, please contact:

**Sreyphea Chheang**  
Email: sreyphea.chheang@uca.fr  
GitHub: <https://github.com/spchheang>
