# Forecasting-electron-flux-in-near-earth-plasma-Sheet-using-solar-wind-parameters

🧭 Project Overview
This project aims to forecast Solar Spectral Irradiance (SSI) at a wavelength of 59.5 nm using machine learning techniques. SSI plays a crucial role in understanding solar-terrestrial interactions, especially its influence on the ionosphere, satellite communication, and space weather events. To achieve this, we use ensemble learning algorithms — specifically XGBoost, AdaBoost, and CatBoost — trained on historical space weather data.

🎯 Objective
To predict solar spectral irradiance (SSI) at 59.5 nm using a combination of solar wind parameters and interplanetary magnetic field (IMF) data.

To apply ensemble models for more robust and interpretable forecasting of SSI.

To analyze the effectiveness of different ensemble algorithms on the same dataset for comparative evaluation.

📊 Dataset Summary
🔹 Data Collection
Input Features Source: OMNIWeb (NASA)

Collected hourly solar wind and IMF data of 7 years  (at 5 min resolution).

OMINI dataset link :- https://omniweb.gsfc.nasa.gov/form/omni_min.html
FISM dataset link:-http://lasp.colorado.edu/eve/data_access/evewebdata/fism/flare_bands/

Features used:

n – Proton density

V – Solar wind speed

BY, BZ – Components of the Interplanetary Magnetic Field (IMF)

Output Target Source: FISM (Flare Irradiance Spectral Model)

Provides model-generated SSI values based on empirical solar measurements.

Target used: ssi_59.5nm

🔹 Time Periods
Training Data: January 2008 – December 2015

🧹 Preprocessing
Steps followed:
Merge input (OMNI) and output (FISM) datasets by matching timestamps.

Remove invalid values (e.g., 999.999, 99999.99) by replacing with NaN.

Drop or fill missing values (NaNs were dropped in this case).

Convert datetime to standard format and sort data chronologically.

Scale data using MinMaxScaler from sklearn for normalization.

Separate CSVs were created for:

Preprocessed unscaled data

Scaled data (used for model training and testing)

🤖 Models Implemented
The project implemented three ensemble learning models:

1. XGBoost
Tree boosting algorithm with regularization.

Handles high-dimensional structured data well.

2. AdaBoost
Combines multiple weak learners (like decision stumps).

Focuses more on difficult cases through reweighting.

3. CatBoost
Gradient boosting library by Yandex.

Efficient with less hyperparameter tuning and categorical data support.

Each model was trained on the same dataset to compare performance fairly.

🧪 Model Evaluation
After model training, we evaluated the results using the following metrics:

MAE (Mean Absolute Error) – Measures average magnitude of error.

RMSE (Root Mean Square Error) – Penalizes large errors more heavily.

R² Score – Indicates how well predictions match actual data.

Actual vs Predicted Plot – For visual inspection of model performance.

These evaluations help determine the accuracy and generalization ability of each model.

🧰 Tools & Libraries Used
Python 3.10

pandas and numpy for data handling

matplotlib and seaborn for plotting

scikit-learn for preprocessing, metrics, AdaBoost

xgboost for gradient boosting

catboost for efficient ensemble modeling
