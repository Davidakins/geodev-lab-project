# Data Notes

Project: Flood exposure assessment in Kosofe Local Government Area, Lagos State, Nigeria  
Study area: Kosofe LGA  
Working projected CRS: WGS 84 / UTM Zone 31N (EPSG:32631)

## Kosofe administrative boundary

* Source organisation:\*\* GRID3 Nigeria
* Source portal:\*\* https://data.grid3.org/
* Download date:\*\* Not recorded
* Original format:\*\* ESRI Shapefile
* Feature count:\*\* 1
* Geometry type:\*\* Polygon
* Original CRS:\*\* WGS 84 (EPSG:4326)
* Processed CRS:\*\* WGS 84 / UTM Zone 31N (EPSG:32631)
* Approximate area:\*\* 61.46 km²
* Coverage:\*\* Kosofe Local Government Area, Lagos State
* Null values:\*\* No null values were observed in the key identification fields for the single feature.
* Google Earth Engine working copy:\*\* `projects/ee-tommy4demal/assets/Kosofe\\\_Lga`



#### Attribute fields

* globalid` — Text; unique record identifier
* `uniq\\\\\\\_id` — Integer; unique numeric identifier
* `timestamp` — Date; recorded as 2019-08-09
* `editor` — Text; recorded as `nuraddeen.isah`
* `lganame` — Text; `Kosofe`
* `lgacode` — Text; `25013`
* `statename` — Text; `Lagos`
* `statecode` — Text; `LA`
* `source` — Text; `eHA\\\\\\\_Polio`
* `amapcode` — Text; `NIE LAS KSF`



## Sentinel-1 SAR

* Source: European Union/ESA/Copernicus through Google Earth Engine
* Earth Engine collection: `COPERNICUS/S1\\\_GRD`
* Period used: 1 January–31 December 2025
* Bands: VV and VH median backscatter in decibels
* Resolution: 10 m
* Format: GeoTIFF raster
* Purpose: Radar input for later historical flood-event mapping.
* Quality note: Thirty descending-orbit IW scenes intersected the study area. The annual median is an input composite and must not be interpreted as a flood map without event-specific before-and-after analysis.

## Copernicus DEM

* Source: Copernicus through Google Earth Engine
* Earth Engine collection: `COPERNICUS/DEM/GLO30\\\_2024\\\_1`
* Band: DEM/elevation
* Resolution: 30 m
* Format: GeoTIFF raster
* Purpose: Represents terrain elevation and supports identification of low-lying locations.
* Quality note: This is a digital surface model that can include buildings and vegetation. The 30 m resolution is suitable for LGA-scale screening but not property-level drainage assessment.

## JRC Global Surface Water

* Source: European Commission Joint Research Centre/Google
* Earth Engine dataset: `JRC/GSW1\\\_4/GlobalSurfaceWater`
* Temporal coverage: 1984–2021
* Layers used: Seasonality and permanent-water mask
* Resolution: 30 m
* Format: GeoTIFF raster
* Purpose: Identifies persistent surface-water locations and provides the water layer for the Week 4 proximity analysis.
* Quality note: The layer represents long-term detected surface water, not every drainage channel or short-lived flood pathway. Zero means the selected water condition was not detected at that pixel.

## Dynamic World built-up data

* Source: Google and World Resources Institute through Google Earth Engine
* Earth Engine collection: `GOOGLE/DYNAMICWORLD/V1`
* Period used: 1 January–31 December 2025
* Layers: Mean built probability and conservative binary built-up mask
* Resolution: 10 m
* Format: GeoTIFF raster
* Purpose: Identifies developed land potentially exposed to flooding.
* Quality note: Twenty-one images intersected Kosofe during the selected period. The probability layer records model confidence; the binary mask retains pixels classified as built with mean built probability of at least 0.50.

## OpenStreetMap buildings and roads

* Source: OpenStreetMap contributors
* Access method: Existing local extracts/QuickOSM
* Geometry: Building polygons and road lines
* Original CRS: WGS 84 (EPSG:4326)
* Processed CRS: WGS 84 / UTM Zone 31N (EPSG:32631)
* Purpose: Building exposure analysis and visual reference.
* Quality note: Coverage is community mapped and may be incomplete or inconsistently tagged. The layers are appropriate for preliminary screening but should not be treated as an authoritative building or road inventory.

## General quality verdict

The datasets are suitable for an initial LGA-scale flood-exposure assessment. They are not sufficient for parcel-level predictions because drainage capacity, field observations, detailed rainfall records and verified flood reports are not yet included.

