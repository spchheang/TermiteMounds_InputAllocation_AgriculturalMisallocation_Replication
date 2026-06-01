### Waterways Data from Humanitarian OpenStreetMap Team

This project uses waterways data from the **Humanitarian OpenStreetMap Team (HOT)** to measure access to nearby water sources in Cambodia.

The dataset used is:

```text
hotosm_khm_waterways_lines_shp
```

This dataset is a shapefile containing mapped waterways and rivers in Cambodia. It is derived from **OpenStreetMap (OSM)** data and made available through the **Humanitarian Data Exchange (HDX)** platform. The prefix **`khm`** refers to Cambodia, while **`waterways_lines`** indicates that the dataset contains line features representing waterways, such as rivers, streams, and canals.

#### Data Source

The waterways shapefile can be downloaded from the Humanitarian Data Exchange (HDX) website:

```text
https://data.humdata.org/dataset/hotosm_khm_waterways
```

#### Data Needed

Download the following dataset:

| Dataset                          | Format    | Source                      | Interpretation                                                     |
| -------------------------------- | --------- | --------------------------- | ------------------------------------------------------------------ |
| `hotosm_khm_waterways_lines_shp` | Shapefile | HOT / OpenStreetMap via HDX | Line features representing mapped waterways and rivers in Cambodia |

#### Purpose of the Dataset

This shapefile is used to calculate the distance from each village to the nearest water source. The resulting distance variable can be used as a geographic control or accessibility measure in the analysis.

For example, after downloading the shapefile, the waterways layer can be used in GIS software such as QGIS, ArcGIS, R, or Python to compute the shortest distance between village locations and nearby rivers, streams, canals, or other mapped waterways.

#### Variable Created

| Variable                 | Description                                                        |
| ------------------------ | ------------------------------------------------------------------ |
| Distance to water source | Distance from each village to the nearest mapped waterway or river |

The waterways data are obtained from the **Humanitarian OpenStreetMap Team (HOT)** through the **Humanitarian Data Exchange (HDX)** platform.
