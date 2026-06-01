### Geographic Characteristics from EarthEnv

This project uses geographic characteristics from the **EarthEnv Global Topography Dataset**, available from the EarthEnv database:

```text
http://www.earthenv.org/topography
```

The topographic variables are based on Amatulli et al. (2018), which provides a standardized global suite of topographic variables for environmental and biodiversity modeling:

```text
https://www.nature.com/articles/sdata201840
```

EarthEnv provides standardized environmental layers, including topographic variables derived from digital elevation models. The variables used in this project are derived from the **SRTM4.1dev** source and are aggregated using the **mean** value at **1 km resolution**.

#### Data Needed from EarthEnv

Download the following topographic variables:

| Dataset / Variable Name  | Aggregation | Source     | Resolution | Interpretation                                                                         |
| ------------------------ | ----------: | ---------- | ---------: | -------------------------------------------------------------------------------------- |
| Elevation                |        Mean | SRTM4.1dev |       1 km | Average elevation of the spatial unit                                                  |
| Slope                    |        Mean | SRTM4.1dev |       1 km | Average steepness of the terrain                                                       |
| Terrain Ruggedness Index |        Mean | SRTM4.1dev |       1 km | Average elevation difference between adjacent cells in a Digital Elevation Model (DEM) |

#### Variable Descriptions

* **Elevation (Mean):** Measures the average height above sea level within each spatial unit.
* **Slope (Mean):** Measures the average steepness of the land surface.
* **Terrain Ruggedness Index (Mean):** Measures the amount of elevation difference between adjacent cells of a Digital Elevation Model (DEM). Higher values indicate more rugged or uneven terrain.

These geographic characteristics, including terrain ruggedness, elevation, and slope, are calculated using information provided by the **EarthEnv Global Topography Dataset** (Amatulli et al., 2018).
