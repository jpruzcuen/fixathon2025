# fixathon2025
This project trains an XGBoost regression model to predict post-disturbance NDVI values using meteorological variables, lagged features, and rolling statistics. Each plot is treated as a time series to avoid data leakage by applying a group-wise chronological train–test split. After prediction, NDVI loss is converted into damaged forest area based on the spatial resolution of the satellite data. The trained model is saved in XGBoost's native format (model.json) for efficient reuse in downstream inference pipelines.

To load our trained model:
model = XGBRegressor()
model.load_model("model.json")

And then predictions can be made like this:
y_pred = model.predict(new_data)
