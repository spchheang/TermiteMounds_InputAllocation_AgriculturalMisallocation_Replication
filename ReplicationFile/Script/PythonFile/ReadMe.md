
# SoilGrids Download Instructions

This repository uses soil covariates downloaded from the SoilGrids database developed by :contentReference[oaicite:0]{index=0}.

## SoilGrids Website

Download data from:

- :contentReference[oaicite:1]{index=1}

Navigation path:

1. Click **Download**
2. Select **SoilGrids**
3. Choose the desired soil layer(s)

---

# Download Settings

## Version

Use the following SoilGrids release:

- **SoilGrids v2.0**
- **Release date:** January 12, 2026
- **Spatial resolution:** 250 m

---

# Soil Variables

Download the following layers:

- Clay content (%)
- Sand (%)
- Bulk density
- pH
- SOC (Soil Organic Carbon)

Additional contextual controls (optional but recommended):

- Coarse fragments (%)
- CEC (Cation Exchange Capacity)

---

# Depth Intervals

For each variable, download the following depth layers:

- 0–5 cm
- 5–15 cm
- 15–30 cm

Statistic to select:

- **Mean**

---

# Geographic Extent (Cambodia)

Use the following bounding box:

| Coordinate | Minimum | Maximum |
|---|---|---|
| Longitude | 102.3000 | 107.6000 |
| Latitude | 10.4000 | 14.7000 |

> **Note:**  
> The bounding box is based on a 2° × 2° tile (~200 × 200 km).

---

# Soil Texture Variables

The main soil texture variables are:

- Clay (%)
- Sand (%)
- Silt (%)

---

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
