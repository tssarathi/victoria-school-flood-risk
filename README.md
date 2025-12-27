# Are Our Schools Safe? A Spatial Analysis of Flood Exposure and Socio-Economic Disadvantage in North Central Victoria

**Assignment 4: Major Project | Spatial Data Analytics (GEOM90006) | Semester 1, 2025 | Group 37**

## Overview

This project examines the intersection of flood risk and socio-economic disadvantage for government schools in North Central Victoria, Australia. Using spatial analysis techniques, we investigate whether schools are disproportionately located in flood-prone areas and if those at risk tend to be in more disadvantaged communities.

## Motivation

Severe flooding is one of the most frequent and costly natural hazards in Victoria. The October 2022 Victorian floods devastated parts of the state, with long-term economic impacts projected to exceed $600 million by 2030. Socio-economic disadvantage can exacerbate flood impacts, as communities with lower socio-economic status often have fewer resources to prepare for, respond to, and recover from disasters. This analysis seeks to understand where the most vulnerable schools are located and why, ensuring safe and resilient learning environments.

## Study Area

The study focuses on five Local Government Areas (LGAs) in North Central Victoria that were significantly affected by the 2022 floods:

- **Mitchell**
- **Campaspe** 
- **Greater Bendigo**
- **Greater Shepparton**
- **Strathbogie**

These LGAs were selected for their diverse socio-economic profiles, varied geography, and different levels of flood exposure, enabling meaningful comparisons across the region.

## Research Questions

1. **Are government schools disproportionately located in flood-prone zones compared to safer areas?**
2. **Is there a spatial association between flood-exposed schools and low socio-economic status areas?**
3. **Are there spatial clusters of vulnerable schools?**

## Data Sources

- **School Locations (2021)**: Victorian Department of Education and Training point dataset
- **Socio-Economic Index (IRSD 2021)**: ABS SEIFA Index of Relative Socio-Economic Disadvantage at SA2 level
- **Census 2021 School Enrolments**: ABS Census General Community Profile (Table G15) at SA2 level
- **LGA Boundaries**: Vicmap Administrative boundaries from DELWP
- **Flood Extent (1-in-100 Year)**: Polygon layer of 1% Annual Exceedance Probability flood zones
- **Digital Elevation Model (DEM 10m)**: High-resolution raster DEM from Vicmap Elevation
- **SA2 Boundaries**: ABS ASGS SA2 digital boundary file (2021 edition)

All data were projected to EPSG:7845 (GDA2020 MGA zone) for consistency.

## Spatial Analysis Methods

### 1. Exploratory Point Pattern Analysis
- Average Nearest Neighbor (ANN) analysis
- Ripley's K and L functions
- Ripley's G and F functions
- Quadrat Count analysis with Variance-to-Mean Ratio
- Kernel Density Estimation (KDE)

### 2. Areal Spatial Autocorrelation
- Global measures: Moran's I, Geary's C, Getis-Ord General G
- Local measures: Local Moran's I (LISA), Getis-Ord Gi* (Hotspot analysis)

### 3. Raster and Flood Exposure Analysis
- School elevation extraction and distribution analysis
- Distance to nearest flood zone boundary calculations
- Watershed (drainage) analysis using DEM

### 4. Geographically Weighted Regression (GWR)
- Spatially varying relationships between environmental factors and flood-safe school proportions
- Key predictors: average school elevation, mean distance to flood zones, flood intersection count

## Key Findings

### 1. High Flood Exposure Rates
- **Greater Shepparton**: ~69% of government schools (20 out of 29) in flood zones
- **Strathbogie & Campaspe**: ~65% of schools in flood zones
- **Greater Bendigo**: ~30% of schools in flood zones
- **Mitchell Shire**: Only ~7-8% of schools in flood zones

### 2. Environmental Justice Concern
Areas with lower socio-economic status (lower SEIFA scores) generally contain more flood-exposed schools, indicating that disadvantaged communities bear a greater share of educational infrastructure risk.

### 3. Geographic Hotspots of Vulnerability
Spatial clustering analysis revealed distinct hotspots along major river corridors in north-central Victoria, where multiple at-risk schools serve disadvantaged populations. Conversely, higher-elevation districts in the west showed clusters of flood-safe schools.

### 4. Topography Matters
- Flood-exposed schools sit at significantly lower elevations on average
- Schools farther from floodplain boundaries tend to be safer
- Mitchell Shire schools average several kilometers from flood zones, while flood-prone LGAs average only a few hundred meters

### 5. GWR Results
Average distance of schools from flood zones was the strongest predictor of an SA2's safe-school proportion, with spatial variation in coefficient strength across the region.

## Policy Implications & Recommendations

1. **Prioritize at-risk schools for upgrades**: Fast-track infrastructure improvements for schools in identified hotspots
2. **Integrate flood risk into school site planning**: Incorporate flood hazard data into decision-making for new schools
3. **Address social vulnerability through funding**: Direct additional support to disadvantaged areas with high flood exposure
4. **Implement emergency response plans**: Develop detailed flood emergency plans for schools in or near flood zones

These recommendations align with **[SDG 4](https://www.un.org/sustainabledevelopment/education/)** (Quality Education) and **[SDG 11](https://www.un.org/sustainabledevelopment/cities/)** (Sustainable Cities and Communities).

## Project Structure

```
victoria-school-flood-risk/
├── A4.ipynb              # Main analysis notebook
├── README.md             # This file
├── Data/
│   ├── Point/           # School locations, SEIFA, Census data
│   ├── Polygon/         # LGA boundaries, flood extents, SA2 boundaries
│   └── Raster/          # DEM elevation data
└── Documentations/       # Project proposal and documentation
```

For full details and to access the code and data, please refer to the [GitHub repository](https://github.com/tssarathi/victoria-school-flood-risk).

## Usage

The main analysis is contained in [`A4.ipynb`](A4.ipynb). To reproduce the results:

1. Ensure all data files are in the correct `Data/` subdirectories
2. Install required Python packages (GeoPandas, PySAL, rasterio, etc.)
3. Run the notebook cells sequentially

## Authors

Sarathi T S, Nikki Mo & Xie Mingjun

---

**Note**: This analysis was conducted as part of the Spatial Data Analytics course (GEOM90006) at the University of Melbourne, Semester 1, 2025. For detailed methodology, code, and complete references, see [`A4.ipynb`](A4.ipynb).
