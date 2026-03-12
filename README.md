# Cyclone-Driven Changes in Ocean Thermodynamics using Earthformer

This project investigates cyclone-driven variability in ocean thermodynamic properties in the **Chilika coastal region** using a deep learning spatiotemporal model.

The study applies the Earthformer Cuboid Transformer architecture implemented in PyTorch to predict oceanographic conditions during tropical cyclones.

The model learns relationships between **cyclonic forcing and ocean state variables** to forecast changes in temperature, salinity, and sea surface height.

---

## Study Area

The study focuses on the **Chilika coastal ocean region (Bay of Bengal)** affected by tropical cyclones.

Spatial domain used in the model:

Latitude: 18.3° – 19.3°  
Longitude: 85.32° – 86.32°

Ocean variables are analyzed across multiple depth levels up to **100 m**.

---

## Data Sources

Oceanographic data was obtained from the **Copernicus Marine Environment Monitoring Service (CMEMS-ARMOR3D)**.

Cyclone track data was obtained from the **International Best Track Archive for Climate Stewardship (IBTrACS)**.

For each cyclone event:

- 15 days before cyclone formation
- 15 days after cyclone formation

were downloaded to capture the full ocean response.

---

## Oceanographic Variables

The dataset contains the following variables:

| Variable | Description |
|--------|-------------|
| to | Ocean temperature |
| so | Salinity |
| ugo | Geostrophic zonal velocity |
| vgo | Geostrophic meridional velocity |
| zo | Absolute sea surface height |

The dataset is **4-dimensional** with coordinates:

(time, depth, latitude, longitude)

---

## Cyclonic Forcing

Cyclonic forcing was calculated using:

- Cyclone wind intensity
- Distance between the cyclone center and the study area

derived from IBTrACS cyclone track data.

This forcing term is included as an additional input feature to the model.

---

## Machine Learning Model

The model used in this study is the **Earthformer Cuboid Transformer**, a deep learning architecture designed for spatiotemporal Earth system prediction.

Model inputs include:

- Oceanographic variables
- Cyclonic forcing
- Spatiotemporal grid information

The model predicts future ocean states during cyclone events.

---

## Project Pipeline

Raw NetCDF Ocean Data  
↓  
Data Inspection and Cleaning  
↓  
Feature Engineering  
↓  
Conversion to NumPy Arrays  
↓  
Earthformer Model Training  
↓  
Prediction of Ocean Fields  
↓  
Post-processing and Reconstruction  
↓  
Comparison with Observed Data  

---

## Repository Structure

```
project
│
├── data
│   raw and processed datasets
│
├── preprocessing
│   scripts for cleaning and preparing NetCDF data
│
├── model
│   Earthformer training scripts
│
├── postprocessing
│   reconstruction of physical ocean fields
│
├── results
│   visualization and analysis notebooks
│
└── README.md
```

---

## Model Outputs

The trained model produces predictions for:

- Temperature (to)
- Salinity (so)
- Absolute sea surface height (zo)

Outputs are reconstructed into NetCDF datasets for scientific interpretation.

Each dataset contains:

(time, depth, latitude, longitude)

---

## Evaluation Metrics

Model performance is evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Coefficient of Determination (R²)

---

## Tools and Libraries

- Python  
- PyTorch  
- NumPy  
- xarray  
- Matplotlib  

---

## Project Objective

This project explores how **deep learning models can capture cyclone-driven ocean dynamics** and provide insights into ocean thermodynamic variability in coastal environments.

The study demonstrates how **spatiotemporal transformer architectures** can be applied to Earth system datasets for environmental prediction tasks.
