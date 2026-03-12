# Preprocessing

This folder contains scripts used to prepare the dataset for model training.

## Steps

1. Calculate the cyclonic forcing using cyclone wind intensity and the distance of the cyclone from the study area.
2. Inspect and explore the oceanographic dataset.
3. Clean the NetCDF oceanographic data.
4. Extract the relevant variables: temperature, salinity, geostrophic zonal velocity, geostrophic meridional velocity, and absolute sea surface height.
5. Convert the cleaned data into NumPy arrays.
6. Prepare the arrays in the format required for the Earthformer model.
The resulting processed arrays are stored in the `data/` directory and are later converted into PyTorch tensors during model training.
