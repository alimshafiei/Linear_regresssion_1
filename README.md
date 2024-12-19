# Linear Regression Model

## Project Overview
This project demonstrates a linear regression model using the California Housing dataset. The goal is to predict house prices based on various features.

## Dataset
- **Source**: California Housing dataset from `sklearn.datasets`
- **Features**: `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`
- **Number of Rows**: 20640
- **Target**: House prices

## Model
- **Linear Regression**: The target variable is the house price, which is a continuous feature, so a regression model is used for prediction.

## Code Explanation

### Data Loading
Loading the California Housing dataset from `sklearn` using the `fetch_california_housing()` method.

### Data Preprocessing
- Run `shape`, `describe`, `info`, `isnull`, `dtypes`, `corr`, `nunique`, `memory_usage`, and `memory_usage(deep)` to get an overview of the dataset.
- All rows have valid values, so no rows were dropped.
- The correlation matrix showed that `MedInc` has the highest correlation (0.688) with the target variable `Price`, so `MedInc` was selected for regression.
- Split the dataset into 75% training data and 25% test data using `train_test_split`.
- Standardized the `X_train` and `X_test` data using `StandardScaler` and reshaped them to 2D.

### Build and Train Model
- Created a linear regression model (`model_linear`) and trained it on the standardized training data (`X_train_scaled`).

### Make Predictions
- Made predictions using the trained model on the standardized test data (`y_pred = model_linear.predict(X_test_scaled)`).

### Evaluation
- Evaluated the linear model using MSE, R-squared, and MAE metrics:
  - **Mean Squared Error (MSE)**: 0.7001962368292408
  - **R-squared**: 0.47083837938023376
  - **Mean Absolute Error (MAE)**: 0.6268970462646626

### Visualize the Results
- Used a scatter plot to visualize the actual vs. predicted prices.

### Combining Features and Making `model_combined`
- Combined three features (`MedInc`, `AveRooms`, `HouseAge`) to improve the model.
- Split the data, built, and trained a new model (`model_combined`).
- Evaluated the new model:
  - **Mean Squared Error (Combined)**: 0.6459618355890845
  - **R-squared (Combined)**: 0.5118251230159077
  - **Mean Absolute Error (Combined)**: 0.5991743182745098

### Comparing `model_linear` with `model_combined`
- Combining features reduced MSE and MAE, indicating increased model accuracy.
- The increase in R-squared suggests better model fit but may make interpretation more complex.

### Feature Engineering 1: Interaction Features
- Created a new feature `MedInc_HouseAge` by multiplying `MedInc` and `HouseAge`.
- Built and trained a new model (`model_IntAct1`) using this feature.
- Evaluated the model:
  - **Mean Squared Error (IntAct1)**: 0.8493489887287555
  - **R-squared (IntAct1)**: 0.35811867629749194
  - **Mean Absolute Error (IntAct1)**: 0.715269580432741

### Comparing `model_linear` with `model_IntAct1`
- Both MSE and MAE increased, indicating that the interaction feature did not improve the model.

### Feature Engineering 2: Interaction Features
- Created a new feature `AveRooms_HouseAge` by multiplying `AveRooms` and `HouseAge`.
- Built and trained a new model (`model_IntAct2`) using this feature.
- Evaluated the model:
  - **Mean Squared Error (IntAct2)**: 1.2774818800086682
  - **R-squared (IntAct2)**: 0.03456438869346601
  - **Mean Absolute Error (IntAct2)**: 0.8812515362801716

### Comparing `model_linear` with `model_IntAct2`
- Both MSE and MAE increased, indicating that this interaction feature also did not improve the model.

## Conclusion
In linear regression, combining features generally improves prediction accuracy more effectively than creating interaction features.

## License This project is licensed under the MIT License - see the LICENSE file for details.
## © 2024 Ali M Shafiei. All rights reserved.

 
