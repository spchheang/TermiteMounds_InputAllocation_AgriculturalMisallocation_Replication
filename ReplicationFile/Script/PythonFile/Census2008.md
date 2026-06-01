### Population Census 2008 Data

This project uses the **Population Census 2008** dataset for Cambodia. The dataset provides population and household information for the Kingdom of Cambodia in 2008.

The data include key demographic variables such as:

* Total population
* Male population
* Female population
* Number of households
* Population density
* Administrative boundary information

#### Data Source

The Population Census 2008 dataset can be downloaded from Open Development Cambodia:

[Population Census 2008 – Open Development Cambodia](https://data.opendevelopmentcambodia.net/dataset/census-2008)

#### Data Needed

Download the shapefiles included in the dataset for the following administrative levels:

| Administrative Level | Description                                   |
| -------------------- | --------------------------------------------- |
| Province             | Provincial-level population and boundary data |
| District             | District-level population and boundary data   |
| Commune              | Commune-level population and boundary data    |
| Village              | Village-level population and boundary data    |

#### Purpose of the Dataset

The census shapefiles are used to obtain population and household characteristics at different administrative levels in Cambodia. These variables can be used as demographic controls or merged with other spatial datasets for geographic and socioeconomic analysis.

For this project, the **village-level shapefile** is also used to create geographic characteristics within a **1 km buffer zone around each village area**. The buffer zone is used to extract or calculate spatial variables from other geographic datasets, such as elevation, slope, terrain ruggedness, climate, soil characteristics, and distance to nearby water sources.
