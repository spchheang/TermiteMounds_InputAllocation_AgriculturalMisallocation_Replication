# Replication Code for *Observable Ecological Heterogeneity and Agricultural Misallocation: Evidence from Cambodian Rice Plots*

This repository contains the replication files for the working paper:

**_Observable Ecological Heterogeneity and Agricultural Misallocation: Evidence from Cambodian Rice Plots_.**

The paper studies agricultural misallocation in Cambodian rice production using plot-level panel data from the Chrey Bak catchment in Kampong Chhnang Province, Cambodia. The analysis examines whether land and labor are allocated efficiently across rice plots when part of productivity heterogeneity is observable through termite-mound-soil use.

## Author

**Sreyphea Chheang**  
Postdoctoral Fellow, CERDI, Université Clermont Auvergne  
Ph.D. in Economics, York University  
GitHub: <https://github.com/spchheang>

## Project Overview

The replication files use **Python** and **Stata** to:

- prepare village-level geographic and climate variables;
- clean and merge plot-level survey data;
- estimate production-function parameters for land and labor;
- construct residual-based plot-level productivity measures;
- adjust measured productivity for measurement error and transitory shocks;
- calculate output gains from reallocating land and labor under an efficient benchmark;
- decompose total gains into within-type and between-type components; and
- produce the main tables, appendix tables, and figures used in the paper.

The main empirical classification is based on **termite-mound-soil use**. Plots that use termite-mound soil as a soil amendment are classified as **TM-soil plots**, while plots that do not use termite-mound soil are classified as **NTM-soil plots**. The paper also discusses termite-mound presence, but termite-mound-soil use is the preferred classification because it is more directly related to the productivity comparison used in the empirical framework.

## Research Question

The paper asks whether observed land and labor allocations across rice plots are close to the allocation implied by an efficient benchmark. It also asks whether output losses arise mainly from:

1. misallocation **between** TM-soil and NTM-soil plots; or
2. misallocation **within** each observable plot type.

This distinction matters because large between-type gains would suggest that the broad allocation of inputs between TM-soil and NTM-soil plots is the main problem. Large within-type gains would instead suggest that land and labor are not allocated efficiently among plots that appear similar according to this observable ecological classification.

## Main Findings Reproduced by the Code

The replication files reproduce the paper's main results:

- Efficient reallocation of land and labor would increase aggregate rice output by about **45 percent** at the Chrey Bak catchment level after adjusting measured productivity for measurement error and transitory shocks.
- Most adjusted gains come from reallocating inputs **within** the same observable ecological type.
- At the catchment level, within-type reallocation accounts for about **95 percent** of total adjusted gains, while between-type reallocation accounts for about **5 percent**.
- Positive efficiency gains remain when reallocation is restricted to districts, communes, or villages.
- Robustness checks show that the magnitude of estimated gains varies across specifications, but the qualitative conclusion remains the same: within-type misallocation is the dominant source of output loss.

## Data Sources

### 1. Plot-Level Survey Data

The main data source is the plot-level survey dataset from Lao et al. (2024):

[Lao et al. (2024), Farmer economic and social surveys in the Chrey Bak catchment, Cambodia](https://dataverse.ird.fr/dataset.xhtml?persistentId=doi:10.23708/U6WMCP)

The survey covers rice farmers in Kampong Chhnang Province, Cambodia, during the 2021--2023 rice-growing seasons. The sample used in the paper contains **3,424 plot-season observations**, covering **1,144 unique plots**, **594 farmers**, **92 villages**, **21 communes**, and **four districts**.

The survey includes information on:

- rice output;
- land input;
- labor input;
- seed, fertilizer, pesticide, and other production inputs;
- termite-mound presence;
- termite-mound-soil use;
- household characteristics;
- plot characteristics; and
- village, commune, district, season, and year identifiers.

The distinction between **termite-mound presence** and **termite-mound-soil use** is important. Termite-mound presence captures an ecological feature of the plot, while termite-mound-soil use captures a farmer's soil-amendment decision.

### 2. Geographic and Climate Data

The replication files also construct village-level geographic and climate variables. These variables are merged with the plot-level survey data and used in robustness checks.

The geographic and climate variables include:

- soil texture and soil properties;
- elevation and terrain characteristics;
- climate variables;
- waterway and distance-to-water measures;
- village coordinates;
- administrative boundaries; and
- the Chrey Bak catchment boundary.

## Software Requirements

The replication package uses **Python** and **Stata**.

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

The main Python setup file is:

```text
0_Setup.ipynb
```

### Stata

Stata is used for data cleaning, estimation, productivity construction, efficiency calculations, decomposition analysis, robustness checks, and table generation.

The main Stata file is:

```text
0_master.do
```

## Repository Structure

The replication package is organized as follows:

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

## Replication Workflow

### Prepare the Raw Data Folder

Place the required raw datasets in the `RawData/` folder. Some raw datasets may not be included directly in this repository because of data-access or data-use restrictions. The plot-level survey data can be obtained from the IRD Dataverse link listed above.

### Set Project Paths

Before running the code, edit the project paths in the Python setup notebook and the Stata master file.

In Python, update the base directory in:

```text
Python/0_Setup.ipynb
```

In Stata, update the project path in:

```stata
global PATH "/your/project/path"
```

inside:

```text
StataFile/0_master.do
```

### Run the Python Files

Run the Python notebooks first if you need to reconstruct the village-level geographic and climate variables. The Python workflow prepares files such as:

```text
CB_District.kml
TM_Village.csv
TM_Village_with_geo_climate_1km.csv
TM_Village_with_geo_climate_1km_waterdist.csv
```

The Python workflow:

1. loads administrative and catchment boundary files;
2. loads village coordinates;
3. extracts soil, terrain, climate, and water-access variables;
4. calculates village-level geographic characteristics; and
5. exports the processed geographic and climate variables for use in Stata.

### Run the Stata Master File

After preparing the required input files, run:

```text
StataFile/0_master.do
```

The master file runs the Stata scripts in order and produces the cleaned datasets, productivity measures, efficiency-gain calculations, decomposition results, robustness checks, tables, and figures.

### Check Outputs

The main outputs are saved in the folders defined in `0_master.do`, including:

```text
Data/
Figure/
Table/
```

## Stata Workflow Details

The Stata workflow performs the following main tasks:

1. **Data cleaning and merging**  
   Cleans plot-level survey data and merges it with geographic and climate variables.

2. **Production-function estimation**  
   Estimates a Cobb--Douglas production function using land and labor as the main inputs.

3. **Productivity construction**  
   Constructs residual-based plot-level total factor productivity.

4. **Productivity adjustment**  
   Adjusts measured productivity to reduce the influence of measurement error and transitory shocks.

5. **Mean-productivity comparison**  
   Tests productivity differences between TM-soil and NTM-soil plots.

6. **Efficiency-gain calculation**  
   Compares observed land and labor allocations with the efficient benchmark at the catchment, district, commune, and village levels.

7. **Decomposition analysis**  
   Decomposes total output gains into within-type and between-type components.

8. **Group contribution analysis**  
   Calculates how TM-soil and NTM-soil plots contribute to total efficiency gains.

9. **Farm-level analysis**  
   Repeats the efficiency and decomposition exercises at the farm or household level.

10. **Robustness checks**  
    Runs alternative specifications, including IV-CRE productivity estimates and models with additional household and geographic controls.

11. **Tables and figures**  
    Exports summary statistics, production-function estimates, efficiency results, decomposition tables, robustness tables, and figures.

## Main Stata Scripts

| Script | Purpose |
|---|---|
| `4_Cleaned_Merged_Data.do` | Cleans and merges plot-level survey data with geographic and climate variables. |
| `5_1_Cal_betaL_betaN.do` | Estimates production-function parameters for land and labor. |
| `6_2_TFP_VC_Con_Winsorize_FullSample.do` | Constructs plot-level productivity and applies the benchmark productivity adjustment. |
| `6_2_1_TFP_VC_Con_Winsorize_FullSample_Type.do` | Constructs productivity measures by observable plot type. |
| `6_3_Test_mean_TFP.do` | Tests mean productivity differences across plot types. |
| `6_4_Stats_Tab.do` | Produces summary-statistics tables. |
| `6_5_TFP_VC_Con_Winsorize_FullSample_IVCRE.do` | Constructs productivity measures using the IV-CRE specification. |
| `7_1_Cal_Efficiency.do` | Calculates total efficiency gains from reallocating land and labor. |
| `7_2_Cal_Share_Efficiency.do` | Decomposes gains into within-type and between-type components. |
| `7_3_Cal_Share_Efficiency_ByGroup.do` | Calculates the contribution of TM-soil and NTM-soil plots to total gains. |
| `7_4_Cal_Efficiency_HH.do` | Calculates farm- or household-level efficiency gains. |
| `7_5_Cal_Share_Efficiency_HH.do` | Decomposes farm- or household-level efficiency gains. |
| `7_6_Cal_Share_Efficiency_ByGroup_HH.do` | Calculates group contributions at the farm or household level. |
| `7_7_Cal_Efficiency_IVCRE.do` | Calculates efficiency gains using the IV-CRE productivity specification. |
| `8_1_Cal_Efficiency_MOD.do` | Runs modified/robustness efficiency calculations. |
| `8_2_Cal_Share_Efficiency_MOD.do` | Runs modified/robustness decomposition calculations. |
| `8_3_Cal_Share_Efficiency_ByGroup_MOD.do` | Runs modified/robustness group-contribution calculations. |
| `8_4_Cal_betaL_betaN_MOD.do` | Estimates modified/robustness production-function parameters. |
| `8_5_TFP_VC_Con_Winsorize_FullSample_MOD.do` | Constructs modified/robustness productivity measures. |

## Outputs Produced by the Code

The code produces:

- cleaned analysis datasets;
- village-level geographic and climate variables;
- production-function parameter estimates;
- residual-based plot-level productivity measures;
- adjusted productivity measures;
- mean-productivity comparisons by plot type;
- efficiency-gain estimates by geographic level;
- within-type and between-type decomposition results;
- contribution of TM-soil and NTM-soil plots to total gains;
- farm-level efficiency and decomposition results;
- robustness-check results;
- LaTeX tables; and
- figures used in the paper.

## Notes on Interpretation

The benchmark results use the adjusted productivity measure because unadjusted productivity may reflect measurement error and transitory shocks. The adjusted measure provides a more conservative estimate of persistent plot-level productivity differences.

The decomposition should be interpreted carefully. A small between-type component does not mean that termite-mound-soil use is unimportant. Instead, it means that most estimated output losses come from the allocation of land and labor among plots within the same TM-soil or NTM-soil group.

The code identifies the size and structure of misallocation, but it does not identify the exact mechanisms behind it. Possible mechanisms include information frictions, plot distance, seasonal labor constraints, hiring frictions, and within-household allocation decisions.

## Citation

If you use this replication package, please cite the paper and the data source.

### Paper

```text
Chheang, S., Marchand, S., and Lao, C. 2026. Observable Ecological Heterogeneity and Agricultural Misallocation: Evidence from Cambodian Rice Plots. Working paper.
```

### Data

```text
Lao, C., Jouquet, P., Sok, K., Marchand, S., and Audibert, M. 2024. Farmer economic and social surveys in the Chrey Bak catchment, Cambodia: Rainy Season Rice Farming Activities, and Perceptions and Usage of Termite Mounds. doi:10.23708/U6WMCP.
```

## Contact

For questions about the replication code, please contact:

**Sreyphea Chheang**  
Email: [spchheang@gmail.com](mailto:spchheang@gmail.com)  
GitHub: <https://github.com/spchheang>
