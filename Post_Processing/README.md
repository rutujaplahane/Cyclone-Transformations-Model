# Postprocessing

This folder contains scripts used to convert the model outputs into physically interpretable oceanographic fields for analysis and comparison.

The Earthformer model outputs **scaled anomaly values** rather than direct physical measurements. Therefore, several postprocessing steps are required to reconstruct the predicted ocean conditions.

## Postprocessing Workflow

The reconstruction pipeline consists of the following steps:

1. **Load model outputs**

   The predicted and true outputs generated during model testing are loaded from NumPy arrays:

   - `Data/Output/Y_pred.npy`
   - `Data/Output/Y_true.npy`

   These arrays contain flattened channel representations of multiple ocean variables across depth levels.

2. **Remove batch dimension**

   The model output shape is converted from:
   (batch, time, latitude, longitude, channels)
   to:
   (time, latitude, longitude, channels)


3. **Separate physical variables**

   Channels corresponding to static depth information and forcing variables are removed to isolate the predicted oceanographic variables.

4. **Reconstruct the depth dimension**

   The flattened channel dimension is reshaped back into a structured 5-dimensional format:
   (time, depth, latitude, longitude, variables)


5. **Inverse scaling**

   The model outputs are converted back to physical units using the global mean and standard deviation used during preprocessing.

6. **Add pre-cyclone mean state**

   The predicted anomalies are added to the **pre-cyclone mean ocean state** to recover the actual oceanographic conditions.

7. **Generate NetCDF outputs**

   The reconstructed datasets are saved as NetCDF files for visualization and scientific analysis.

## Output Files

   The reconstruction produces the following files for the test cyclone:

| File | Description |
|-----|-----|
| `Yaas_Predicted_Actual.nc` | Reconstructed predicted ocean fields |
| `Yaas_True_Actual.nc` | Reconstructed actual ocean fields |
| `Yaas_pre_mean.nc` | Pre-cyclone mean ocean state |

Each dataset contains the following variables:

- `to` — Temperature  
- `so` — Salinity  
- `zo` — Absolute sea surface height  

## Dataset Dimensions

The reconstructed NetCDF files follow the structure:
(time, depth, latitude, longitude)

## Usage

The reconstructed NetCDF datasets can be used for:

- Visualization of ocean variables
- Spatiotemporal comparison of predictions and observations
- Evaluation of model performance
- Scientific interpretation of cyclone-driven ocean dynamics
