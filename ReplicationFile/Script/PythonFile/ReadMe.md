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

Therefore, including all three variables simultaneously in a regression with an intercept creates perfect multicollinearity. To avoid this issue, include only two of the three variables in regression models.

Common specification:

- Clay (%)
- Sand (%)

The omitted variable (e.g., silt) serves as the reference category.

---

# Interpretation of Additional Soil Controls

| Variable | Interpretation |
|---|---|
| SOC | Soil fertility proxy |
| pH | Nutrient availability |
| Bulk density | Soil compaction, root growth, and water infiltration |
| Coarse fragments (%) | Reduces water-holding capacity and rooting volume |
| CEC | Nutrient retention capacity |

---

### Citation

Please cite:

- ISRIC — World Soil Information
- SoilGrids database

Official website: https://soilgrids.org/

