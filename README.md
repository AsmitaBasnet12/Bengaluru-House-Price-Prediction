# Bengaluru House Price Prediction

This project focuses on building a machine learning model to predict house prices in Bengaluru, India, based on various features such as location, size, number of bedrooms, bathrooms, and total square footage. The project includes data cleaning, feature engineering, outlier detection, and the application of regression models.

## Dataset
The dataset used in this project is sourced from Kaggle:
[Bengaluru House Data](https://www.kaggle.com/datasets/pradeepsapparapu/bengaluru-house-datacsv/data)

### Key Features:
- `location`: The location of the house.
- `size`: The size of the house (e.g., 2 BHK, 3 BHK).
- `total_sqft`: The total square footage of the house.
- `bath`: The number of bathrooms.
- `price`: The price of the house (in Lakhs).

## Project Workflow

### 1. **Data Cleaning**
- Handled missing values.
- Converted `total_sqft` to numeric using average values for ranges.
- Cleaned `location` data by standardizing names and grouping less frequent locations under `"other"`.

### 2. **Feature Engineering**
- Created new features like `price_per_sqft` (price per square foot).
- Converted `size` to a numeric feature, `num_bhk`, representing the number of bedrooms.

### 3. **Outlier Detection and Removal**
#### a. Price Per Square Foot (PPSF) Outliers:
- Used the mean and standard deviation to filter out extreme values within each location.

#### b. BHK-Wise Outliers:
- For each location, compared the price per square foot of BHKs with BHK-1. Removed data points where the price per square foot was significantly lower than the average for smaller BHKs.

### 4. **Modeling**
- Split data into training and testing sets.
- Standardized the features using `StandardScaler`.

#### Models Used:
1. **Linear Regression**:
   - Achieved an R² score of 0.84 on the test set.
   - Metrics:
     - Mean Absolute Error (MAE): 19.28
     - Mean Squared Error (MSE): 2332.79
     - Root Mean Squared Error (RMSE): 48.30

2. **Random Forest Regressor**:
   - Achieved an R² score of 0.69 on the test set.
   - Metrics:
     - MAE: 20.96
     - MSE: 4439.12
     - RMSE: 66.63

### 5. **Evaluation**
- Linear Regression performed better due to the small dataset size and the simplicity of the relationship between features and the target variable.
- Random Forest struggled with overfitting and the limited size of the dataset.

## How to Use
### Prerequisites:
- Python 3.7+
- Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn

## Results
- The best-performing model was Linear Regression with an R² score of 0.84.
- The project demonstrated the importance of rigorous data preprocessing and outlier removal in improving model performance.

## Future Work
- Incorporate more advanced models like Gradient Boosting or XGBoost.
- Explore hyperparameter tuning for Random Forest.
- Enrich the dataset with additional features like proximity to amenities or public transport.

## Dataset Acknowledgment
Dataset provided by [Pradeep Sapparapu on Kaggle](https://www.kaggle.com/datasets/pradeepsapparapu/bengaluru-house-datacsv/data).

