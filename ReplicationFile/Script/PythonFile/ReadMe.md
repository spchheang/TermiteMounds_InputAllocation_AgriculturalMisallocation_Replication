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

Optional additional variables:

- Coarse fragments (%)
- CEC (Cation Exchange Capacity)

### Depth Intervals

Download each variable for:

- 0–5 cm
- 5–15 cm
- 15–30 cm

### Geographic Extent (Cambodia)
- Longitude: 102.3000 to 107.6000
- Latitude: 10.4000 to 14.7000

### Variables
- Clay (%)
- Sand (%)
- Bulk density
- pH
- SOC (Soil Organic Carbon)
- Coarse fragments (%)
- CEC (Cation Exchange Capacity)

# Depth Intervals
For each variable, download the following depth layers:
- 0–5 cm
- 5–15 cm
- 15–30 cm
- 
Statistic to select:
- **Mean**

# Geographic Extent (Cambodia)
Use the following bounding box:

| Coordinate | Minimum | Maximum |
|---|---|---|
| Longitude | 102.3000 | 107.6000 |
| Latitude | 10.4000 | 14.7000 |

> **Note:**  
> The bounding box is based on a 2° × 2° tile (~200 × 200 km).

# Soil Texture Variables

The main soil texture variables are:

- Clay (%)
- Sand (%)
- Silt (%)

# Important Econometric Note

Because soil texture shares are compositional:

\[
\text{Sand} + \text{Silt} + \text{Clay} \approx 100
\]

including all three variables simultaneously in a regression with an intercept creates perfect multicollinearity.

## Recommended Practice

Include only **two** of the three variables in regression models.

Common specification:

- Clay (%)
- Sand (%)

The omitted category (e.g., silt) becomes the reference category.

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

# Citation

Please cite :contentReference[oaicite:2]{index=2} and the SoilGrids database when using these data in replication or derivative work.

Official website:

- :contentReference[oaicite:3]{index=3}
