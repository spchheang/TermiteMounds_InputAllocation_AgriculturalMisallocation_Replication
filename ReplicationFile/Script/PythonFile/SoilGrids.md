## SoilGrids Data Download Instructions

1. Go to the SoilGrids website:  
   https://soilgrids.org/

2. Click:  
   **Download → SoilGrids → Choose Layer**

3. Use the following settings:

### General Settings

- Version: SoilGrids v2.0
- Release date: January 12, 2026
- Resolution: 250 m
- Statistic: Mean

### Variables to Download
- Clay (%)
- Sand (%)
- Bulk density
- pH
- SOC (Soil Organic Carbon)
- Coarse fragments (%)
- CEC (Cation Exchange Capacity)

### Depth Intervals
Download each variable for:
- 0–5 cm
- 5–15 cm
- 15–30 cm
  
Statistic to select:
- **Mean**
  
### Geographic Extent (Cambodia)
Use the following bounding box:

| Coordinate | Minimum | Maximum |
|---|---|---|
| Longitude | 102.3000 | 107.6000 |
| Latitude | 10.4000 | 14.7000 |

> **Note:**  
> The bounding box is based on a 2° × 2° tile (~200 × 200 km).

### Soil Texture Variables
The main soil texture variables are:
- Clay (%)
- Sand (%)
- Silt (%)
Soil texture variables are compositional:

`Sand + Silt + Clay ≈ 100`

To avoid perfect multicollinearity in regression models, only two of the three soil texture variables should be included. In this analysis, Clay (%) and Sand (%) are included, while Silt (%) serves as the omitted reference category.

---

# Interpretation of Soil Controls

| Variable | Interpretation |
|---|---|
| Clay (%) | Soil texture component|
| Sand (%) | Soil texture component|
| Silt (%) | Omitted reference category for soil texture|
| SOC | Soil fertility proxy |
| pH | Nutrient availability |
| Bulk density | Soil compaction, root growth, and water infiltration |
| Coarse fragments (%) | Reduces water-holding capacity and rooting volume |
| CEC | Nutrient retention capacity |

---

### Citation

- ISRIC — World Soil Information
- SoilGrids database

Official website: https://soilgrids.org/

