### Python File: Required Input Data

The Python script requires several external spatial datasets as input files. These datasets are not stored directly in the repository because of file size and source restrictions. Instead, users should download each dataset by following the corresponding instruction files provided in this GitHub repository.

The required data sources include census boundaries, catchment boundaries, topographic variables, soil characteristics, waterways, and climate variables. These files are used to construct geographic and environmental characteristics for the study area, including village-level buffers, distance to water sources, soil properties, climate measures, and terrain characteristics.

#### Required Data Sources

Please download the required input data by following the instructions in the links below:

| Data Source         | Description                                                                                                                                                                                                                                                              | Download Instructions                                                                                                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Census 2008         | Cambodia Population Census 2008 shapefiles, including village-level boundaries used to create 1 km buffer zones around village areas                                                                                                                                     | [Census2008.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/Census2008.md)     |
| Chrey Bak Catchment | Boundary file used to map and define the Chrey Bak Catchment study area in Kampong Chhnang Province, together with the TM_Village.csv file containing village names from the plot-level data used in the paper to map villages within the Chrey Bak Catchment study area | [ChreyBak.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/ChreyBak.md)         |
| EarthEnv            | Topographic variables, including elevation, slope, and terrain ruggedness index                                                                                                                                                                                          | [EarthEnv.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/EarthEnv.md)         |
| SoilGrids           | Soil characteristics, including soil organic carbon, pH, bulk density, coarse fragments, cation exchange capacity, clay, sand, and silt                                                                                                                                  | [SoilGrids.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/SoilGrids.md)       |
| Waterways           | Cambodia waterways shapefile from HOT/OSM, used to calculate distance from villages to the nearest water source                                                                                                                                                          | [WaterWays.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/WaterWays.md)       |
| WorldClim           | Climate variables, including annual mean temperature and annual precipitation                                                                                                                                                                                            | [WorldClimate.md](https://github.com/spchheang/TermiteMounds_InputAllocation_AgriculturalMisallocation_Replication/blob/main/ReplicationFile/Script/PythonFile/WorldClimate.md) |

#### Purpose of the Python Script

The Python script processes and combines these spatial datasets to create geographic, climatic, soil, and environmental variables for the analysis. In particular, the script uses the village-level census shapefile to create a 1 km buffer zone around each village area and then extracts or calculates characteristics from the external spatial datasets within those buffer zones.

The resulting variables are used as geographic and environmental controls in the empirical analysis.


