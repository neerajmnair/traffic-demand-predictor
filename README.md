# Traffic Demand Prediction Project – Gridlock Hackathon

## Objective
Predict normalized traffic demand using the provided training dataset for FlipKart GridLock Hackathon 2.0.

## Phase 1: Dataset Understanding
- Loaded train.csv and test.csv.
- Inspected dataset shape, columns, datatypes, and missing values.
- Identified that demand is the target variable.
- Observed missing values in RoadType, Temperature, and Weather.

## Phase 2: Exploratory Data Analysis (EDA)
- Analyzed the distribution of demand.
- Studied the relationship between:
  - Weather and demand
  - Temperature and demand
  - RoadType and demand
  - NumberofLanes and demand
  - Hour of day and demand
- Generated a correlation heatmap for numerical features.
- Key findings:
  - RoadType and NumberofLanes showed stronger relationships with demand.
  - Weather and Temperature showed relatively weak individual relationships.
  - Demand values were normalized between 0 and 1.

## Phase 3: Preprocessing and Feature Engineering
### Missing Value Handling
- RoadType → filled using mode.
- Weather → filled using mode.
- Temperature → filled using mean.

### Feature Engineering
- Converted timestamp to datetime format.
- Extracted hour from timestamp.
- Dropped the original timestamp column.
- Dropped Index from the training features.

### Encoding
- Applied one-hot encoding to categorical features using pandas get_dummies().
- Aligned train and test feature columns to ensure identical structure.

## Phase 4: Model Training and Evaluation
Split the training data into training and validation sets using train_test_split.

Models evaluated:
1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

Evaluation Metrics:
- R² Score
- Mean Absolute Error (MAE)

Results:
- Linear Regression: R² ≈ 0.863
- Random Forest: R² ≈ 0.949
- Gradient Boosting: R² ≈ 0.825

Random Forest Regressor achieved the best performance and was selected as the final model.

## Phase 5: Final Submission
- Retrained the Random Forest model using the complete training dataset.
- Generated predictions for the test dataset.
- Created submission.csv containing:
  - Index
  - demand

## Conclusion
The project followed a complete machine learning workflow:
Dataset Understanding → EDA → Preprocessing → Feature Engineering → Model Training → Evaluation → Submission Generation.

Random Forest Regressor provided the strongest predictive performance and was used to generate the final submission file.

##Tools Used:
- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
