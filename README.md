### Hi, this is a research repository by Naziru Halilu 👋


[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE) ![QGIS](https://img.shields.io/badge/QGIS-3.x-green)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22741094.svg)](https://doi.org/10.5281/zenodo.22741094)

**GIS Monitoring of Vineyard Ripening (Brix)**

GIS and NDVI-based monitoring of grape ripening (degrees Brix) at Quinta de
Nossa Senhora de Lurdes, a 6-hectare UTAD vineyard in Vila Real, Portugal:
land-use mapping, spectral band analysis, logarithmic regression harvest-date
forecasting, and spatial interpolation of sugar accumulation across five
sampling dates.

📫 halilunaziru73@gmail.com

---

## Problem, Methodology, and Results

**Problem.** Deciding when to harvest is one of the most consequential decisions in viticulture: picking too early loses sugar accumulation and flavour complexity, picking too late risks over-ripening, weather damage, and sugar loss. Relying on isolated field observations alone gives no predictive lead time for labour, winery logistics, or selective parcel harvesting.

**Methodology.** Grape must samples were collected across five dates (15 and 30 July, 6, 15, and 30 August) at Quinta de Nossa Senhora de Lurdes (WGS84 UTM Zone 29N, approximately 6 ha) and measured with a refractometer, using the relationship 1 degree Bx is approximately equal to 0.55 degrees alcohol (Aranha, 2026). Average Brix progression across the five dates was fit to a logarithmic regression against Julian day, and NDVI derived from Sentinel-2 imagery (Red, NIR, and an orthomosaic-corrected NDVI) was used to relate spectral reflectance to spatial ripening variation. Thiessen tessellation was used to interpolate point Brix samples into continuous zones for each sampling date.

**Results.** The regression y = 65.139 ln(x) - 335.44 achieved R-squared = 0.9784, meaning roughly 97.84% of the variation in Brix values across the season is explained by Julian day alone. The model forecasted Brix values of 25.5-27 degrees Bx, the range associated with premium harvest maturity and roughly 14% alcohol potential, occurring near Julian day 256, corresponding to 13 September. Land-use mapping classified the property into agricultural, human-infrastructure, forestry, and water-cover parcels, providing the spatial context for interpreting NDVI and Brix variation across the vineyard.

**Workflow sketch**

![Workflow Sketch](workflow_sketch.png)

[View interactive graphical walkthrough →](https://halilunaziru73-creator.github.io/GIS-Monitoring-of-Vineyard-Ripening-Brix/)

## Guide: Steps Followed

This is my own written account of the GIS workflow, not a reproduction of any
instructor-provided material. The course brief and reference documents used
to design this exercise are cited under **Acknowledgements** below but are
not redistributed in this repository.

1. **Project setup.** Created a QGIS project (`Geopackage/Naziru_Halilu_Brix_Monitoring_(Analysis and NDVI).qgz`) and organised the farm boundary, land-cover, and NDVI raster data as layers.
2. **Land use and occupation mapping.** Digitised and classified the property into agricultural, human-infrastructure, forestry, and water-cover parcels.
3. **Spectral band analysis.** Extracted Red and NIR bands and computed NDVI, both as a direct raster and as an orthomosaic-corrected surface, to characterise spatial vegetation vigour.
4. **Field sampling.** Collected must samples with a refractometer across five dates through the ripening season (15/30 July, 6/15/30 August) and recorded degrees Brix per sample point.
5. **Regression modelling.** Fit a logarithmic regression of average Brix against Julian day to forecast the harvest date and target sugar concentration.
6. **Spatial interpolation.** Applied Thiessen tessellation to each sampling date's point Brix values to generate continuous ripening-zone maps.
7. **Reporting.** Compiled the regression model, harvest forecast, and spatial results into a full written report (`Naziru_HALILU_Monitoring_Alcohol_Degree_Brix_Analysis.pdf`).

## Featuring QGIS Outputs Results

![Farm location](figures/01_farm_location.png)
*Figure 1. Location of Quinta de Nossa Senhora de Lurdes farm area (RGB).*

![Property boundary](figures/02_property_boundary.png)
*Figure 2. Property boundary delineation.*

![Boundary cartography](figures/03_boundary_cartography.png)
*Figure 3. Cartographic layout of the property boundary.*

![Land use and occupation mapping](figures/04_land_use_and_occupation.png)
*Figure 4. Land use and land occupation classification of the estate.*

![NDVI raster](figures/05_ndvi_raster.png)
*Figure 5. NDVI raster derived from Sentinel-2 imagery.*

![Near-infrared band](figures/06_near_infrared_band.png)
*Figure 6. Near-infrared (NIR) reflectance band.*

![Red band](figures/07_red_band.png)
*Figure 7. Red reflectance band.*

![Orthomosaic NDVI](figures/08_orthomosaic_ndvi.png)
*Figure 8. Orthomosaic-corrected NDVI surface.*

![Brix regression analysis](figures/09_brix_regression_analysis.png)
*Figure 9. Logarithmic regression of average Brix against Julian day (R-squared = 0.9784).*

![Brix sample points, 15 July](figures/10_brix_sample_points_15jul.png)
*Figure 10. Georeferenced Brix sample points, 15 July.*

![Brix value map, 15 July](figures/11_brix_value_map_15jul.png)
*Figure 11. Brix value map, 15 July.*

![Thiessen interpolation, 15 July](figures/12_thiessen_interpolation_15jul.png)
*Figure 12. Thiessen tessellation interpolation of Brix values, 15 July.*

![Brix sample points, 30 July](figures/13_brix_sample_points_30jul.png)
*Figure 13. Georeferenced Brix sample points, 30 July.*

![Brix value map, 30 July](figures/14_brix_value_map_30jul.png)
*Figure 14. Brix value map, 30 July.*

![Thiessen interpolation, 30 July](figures/15_thiessen_interpolation_30jul.png)
*Figure 15. Thiessen tessellation interpolation of Brix values, 30 July.*

![Brix sample points, 6 August](figures/16_brix_sample_points_06aug.png)
*Figure 16. Georeferenced Brix sample points, 6 August.*

![Brix value map, 6 August](figures/17_brix_value_map_06aug.png)
*Figure 17. Brix value map, 6 August.*

![Thiessen interpolation, 6 August](figures/18_thiessen_interpolation_06aug.png)
*Figure 18. Thiessen tessellation interpolation of Brix values, 6 August.*

![Brix sample points, 15 August](figures/19_brix_sample_points_15aug.png)
*Figure 19. Georeferenced Brix sample points, 15 August.*

![Brix value map, 15 August](figures/20_brix_value_map_15aug.png)
*Figure 20. Brix value map, 15 August.*

![Thiessen interpolation, 15 August](figures/21_thiessen_interpolation_15aug.png)
*Figure 21. Thiessen tessellation interpolation of Brix values, 15 August.*

![Brix sample points, 30 August](figures/22_brix_sample_points_30aug.png)
*Figure 22. Georeferenced Brix sample points, 30 August.*

![Brix value map, 30 August](figures/23_brix_value_map_30aug.png)
*Figure 23. Brix value map, 30 August.*

![Thiessen interpolation, 30 August](figures/24_thiessen_interpolation_30aug.png)
*Figure 24. Thiessen tessellation interpolation of Brix values, 30 August.*

## Repository Structure

```
figures/                24 map layouts referenced above
Geopackage/              QGIS project file (.qgz)
Grid_NDVI/               NDVI raster layers (note: QTNS_NDVI.tif, 146 MB, could
                         not be uploaded via the GitHub API 100 MB limit)
TCI/                     True Colour Image raster
DBF_XLS_CSV/             Brix sample tabular data
Kml_shape/               QGIS metadata files for land-cover and sampling layers
Styles/                  QGIS layer styling files (.qml)
Naziru_HALILU_Monitoring_Alcohol_Degree_Brix_Analysis.pdf   Full written report
```

## Acknowledgements

This exercise was completed as part of an Erasmus Mundus GIS course under the
supervision of Jose Tadeu Marques Aranha (UTAD). The course brief and
reference material provided for the exercise are not redistributed here;
this repository contains only my own analysis, outputs, and written report.

## License

Code and original written content in this repository are released under the
MIT License (see `LICENSE`). Underlying geospatial data were provided for
coursework purposes; redistribution beyond this academic context should
credit the original data sources noted in the report.
