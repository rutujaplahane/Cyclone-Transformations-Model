# Dataset Description

The data used in this project represents cyclone-driven changes in ocean thermodynamics and was obtained from the Copernicus Marine Environment Monitoring Service (CMEMS) ARMOR3D dataset.

The dataset was extracted for multiple cyclones affecting the Chilika coastal ocean region. For each cyclone, data was collected for:

- 15 days before cyclone formation
- 15 days after cyclone formation

The study area corresponds to the Chilika coastal ocean region. A visualization of the study area can be found in:

results/Results.ipynb

## Data Structure

The dataset is four-dimensional with the following coordinates:

- Time
- Latitude
- Longitude
- Depth

## Oceanographic Variables

The following ocean variables are included:

- Temperature (to)
- Salinity (so)
- Geostrophic zonal velocity (ugo)
- Geostrophic meridional velocity (vgo)
- Absolute sea surface height (zo)

## Cyclonic Forcing

Cyclonic forcing was calculated using:

- Wind intensity
- Distance of the cyclone from the study area

Cyclone track information was obtained from the IBTrACS dataset.

## Data Availability

Due to GitHub file size limitations, the raw dataset is not included in this repository. The processed NumPy arrays used for model training were generated from the NetCDF data using the preprocessing scripts provided in this project.
