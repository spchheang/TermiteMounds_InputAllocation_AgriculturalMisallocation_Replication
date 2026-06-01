### Climatic Measurements from WorldClim

This project uses climatic measurements from the **WorldClim version 2.1 database**, available here:

```text
https://www.worldclim.org/data/worldclim21.html
```

The climate data are based on Fick and Hijmans (2017), which describes the WorldClim 2 database:

```text
https://rmets.onlinelibrary.wiley.com/doi/abs/10.1002/joc.5086
```

WorldClim version 2.1 provides historical climate data for the period **1970–2000**. The data are available at several spatial resolutions. For this project, download the **30 seconds** resolution, which is approximately **1 km²**.

The climatic variables used in this project are from the **Bioclimatic variables** in WorldClim version 2. These variables are derived from monthly temperature and rainfall values and summarize annual climate conditions, seasonality, and extreme or limiting climatic factors.

#### Data Needed from WorldClim

Download the **Bioclimatic variables** from WorldClim version 2.1 at **30 seconds resolution**:

```text
https://www.worldclim.org/data/worldclim21.html
```

The explanation of the bioclimatic variables is available here:

```text
https://www.worldclim.org/data/bioclim.html
```

Use the following variables:

| Variable | Full Name               | Unit | Interpretation                         |
| -------- | ----------------------- | ---: | -------------------------------------- |
| BIO1     | Annual Mean Temperature |   °C | Average annual temperature             |
| BIO12    | Annual Precipitation    |   mm | Total annual rainfall or precipitation |

#### Variable Descriptions

* **BIO1: Annual Mean Temperature**
  Measures the average temperature over the year. This variable is used as the main temperature measure.

* **BIO12: Annual Precipitation**
  Measures the total annual precipitation in millimeters. This variable is used as the main rainfall measure.

Climatic measurements, including rainfall and temperature, are calculated using data from the **WorldClim version 2.1 database** (Fick and Hijmans, 2017).
