# Model

This folder contains the implementation and training script for the Earthformer model used to predict cyclone-driven ocean changes in the Chilika coastal region.

## Model Architecture

The model used in this project is the **Earthformer Cuboid Transformer**, a spatiotemporal transformer architecture designed for Earth system prediction tasks.

Framework: PyTorch  
Model: CuboidTransformerModel (Earthformer)

The model learns spatiotemporal relationships between oceanographic variables such as temperature, salinity, velocity fields, and sea surface height.

## Inputs

The model takes processed NumPy arrays that represent ocean variables across:

- Time
- Latitude
- Longitude
- Depth

Input variables include:

- Temperature (to)
- Salinity (so)
- Geostrophic zonal velocity (ugo)
- Geostrophic meridional velocity (vgo)
- Absolute sea surface height (zo)

## Outputs

The model predicts future ocean conditions for selected variables:

- Temperature
- Salinity
- Absolute sea surface height

## Training

The training script loads the processed NumPy arrays, converts them into PyTorch tensors, and trains the Earthformer model using Mean Squared Error (MSE) loss with the AdamW optimizer.

To train the model:

Model/Model_Training.ipynb

## Model Weights

The trained model weights (`.pt` file) are not included in this repository due to GitHub file size limitations.  
The model can be retrained using the provided training script.

## Evaluation Metrics

Model performance is evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Coefficient of Determination (R²)
