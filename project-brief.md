# Kosofe Flood-Hotspot and Exposure Screening Project

## Part 1: The question

Where has flooding repeatedly occurred during selected historical flood events in Kosofe Local Government Area between 2015 and 2025, and which low-lying built-up areas were most affected?

## Part 2: Why it matters

Flooding disrupts homes, roads, businesses and essential services in low-lying parts of Kosofe. The results could help local emergency managers, planners and community organisations identify recurrent flood hotspots and prioritise affected built-up areas for preparedness and further investigation. This project is also relevant to my interest in using geospatial data to support flood-risk reduction in data-scarce urban areas.

## Part 3: The data I need

- Kosofe Local Government Area boundary.
- Sentinel-1 SAR imagery for detecting historical surface inundation from 2015 to 2025.
- Elevation data for deriving slope and identifying low-lying terrain.
- Land-cover data for identifying built-up areas and other land-cover classes.
- Surface-water occurrence data for excluding permanent water from detected flood extents.
- Verified dates of reported flood events for selecting and validating satellite observations.

## Part 4: Where each dataset comes from

| Dataset | Source and Earth Engine ID | Format / resolution | Intended use |
|---|---|---|---|
| Administrative boundary | [FAO GAUL 2015 Level 2](https://developers.google.com/earth-engine/datasets/catalog/FAO_GAUL_2015_level2) — `FAO/GAUL/2015/level2` | FeatureCollection | Select and clip the analysis to Kosofe LGA. The boundary will be checked against a newer [geoBoundaries Nigeria ADM2](https://www.geoboundaries.org/api/current/gbOpen/NGA/ADM2/) boundary before final use. |
| Historical flood observations | [Sentinel-1 SAR GRD](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD) — `COPERNICUS/S1_GRD` | ImageCollection; commonly 10 m | Compare consistent pre-event and post-event SAR observations to detect likely inundation. |
| Elevation | [Copernicus DEM GLO-30 2024 release](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_DEM_GLO30_2024_1) — `COPERNICUS/DEM/GLO30_2024_1` | ImageCollection; 30 m | Derive elevation and slope and identify relatively low-lying terrain. |
| Land cover and built-up areas | [Dynamic World V1](https://developers.google.com/earth-engine/datasets/catalog/GOOGLE_DYNAMICWORLD_V1) — `GOOGLE/DYNAMICWORLD/V1` | ImageCollection; 10 m | Identify built-up land and other land-cover classes. This avoids adding a separate built-up dataset at the initial stage. |
| Permanent and seasonal water | [JRC Global Surface Water v1.4](https://developers.google.com/earth-engine/datasets/catalog/JRC_GSW1_4_GlobalSurfaceWater) — `JRC/GSW1_4/GlobalSurfaceWater` | Image; 30 m | Mask permanent water and distinguish it from temporary floodwater. |

The raster collections will remain in Earth Engine and be processed server-side rather than downloaded in full. Only data clipped to Kosofe and derived outputs will be exported; their approximate file sizes will be recorded during the first event test because size depends on the selected dates, bands and export format.

The hardest input is a reliable set of historical flood-event dates matched with usable Sentinel-1 observations. I will test this first by selecting one documented event, confirming suitable pre-event and post-event images over Kosofe, and checking whether the resulting inundation pattern is credible. If that test fails, I will narrow or revise the historical component before committing to the complete workflow.

## Part 5: What I would build

I would build a repeatable flood-hotspot and exposure-screening application for Kosofe LGA. It would process Sentinel-1 observations for selected historical events, display recurrent satellite-detected inundation and affected low-lying built-up areas on an interactive map, and generate summary statistics that can be updated when additional events are analysed.

## Scope note

The initial project will identify satellite-detected inundation, recurrent hotspots and affected low-lying built-up areas. It will not initially claim to provide a validated flood forecast; rainfall-triggered alerts may be investigated only after the historical workflow has been developed and tested.
