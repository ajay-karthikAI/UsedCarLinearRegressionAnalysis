# Used Car Linear Regression Analysis

This project analyzes a used-car dataset for Cars4U and builds a baseline linear regression workflow for estimating used-car prices. The notebook walks through data cleaning, feature engineering, exploratory data analysis, and model preparation using Python's data science stack.

## Project Objective

Cars4U wants to understand which vehicle attributes influence resale price and how those insights can guide inventory, marketing, and pricing decisions. This analysis explores questions such as:

- Which numerical features are most related to used-car price?
- How do location, fuel type, transmission, ownership history, and brand affect pricing?
- What preprocessing steps are needed before modeling car prices?
- How can a linear regression model be prepared for price prediction?

## Repository Contents

```text
.
|-- Cars4U.ipynb          # Main analysis notebook
|-- used_cars_data.csv    # Dataset used by the notebook
`-- README.md             # Project documentation
```

## Dataset

The dataset contains 7,253 used-car records with 14 original columns:

| Column | Description |
| --- | --- |
| `S.No.` | Row identifier |
| `Name` | Full car name |
| `Location` | City where the car is listed |
| `Year` | Manufacturing year |
| `Kilometers_Driven` | Total kilometers driven |
| `Fuel_Type` | Fuel category such as Petrol, Diesel, CNG, etc. |
| `Transmission` | Manual or Automatic |
| `Owner_Type` | Ownership history |
| `Mileage` | Mileage value with units in the raw data |
| `Engine` | Engine size with units in the raw data |
| `Power` | Power value with units in the raw data |
| `Seats` | Number of seats |
| `New_Price` | New-car price reference from the dataset |
| `Price` | Used-car resale price target |

## Analysis Workflow

The notebook follows this sequence:

1. Load and inspect the dataset.
2. Review missing values, duplicates, data types, and summary statistics.
3. Remove units from mileage, engine, and power fields.
4. Convert invalid zero values into missing values where appropriate.
5. Engineer additional features, including car age and brand.
6. Explore numeric and categorical variables through histograms, count plots, scatter plots, box plots, pair plots, and correlation heatmaps.
7. Fill missing feature values using grouped medians and modes.
8. Apply log transformation to reduce skew in selected numeric variables.
9. One-hot encode categorical variables.
10. Prepare train/test data for a baseline linear regression model.

## Key Insights

- Newer cars and lower-age vehicles generally show stronger resale value.
- Location matters: some cities show higher average used-car prices than others.
- Automatic cars tend to be priced higher than manual cars.
- Diesel cars are generally more expensive than petrol and CNG cars in this dataset.
- Premium brands and two-seat vehicles appear at the higher end of the price range.
- Common economy brands can support a different sales strategy focused on practicality and affordability.

## Modeling Notes

The notebook prepares a baseline linear regression model using a 70/30 train/test split. After one-hot encoding, the saved notebook shows:

```text
X_train: (5076, 1037)
X_test:  (2176, 1037)
y_train: (5076, 2)
y_test:  (2176, 2)
```

The raw dataset includes rows where `Price` is missing. When rerunning or extending the model, rows without a target `Price` should be excluded before fitting a supervised regression model. For a fuller evaluation, add test-set metrics such as R-squared, MAE, RMSE, and residual plots.

## Requirements

Install the main Python libraries used in the notebook:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/ajay-karthikAI/UsedCarLinearRegressionAnalysis.git
   cd UsedCarLinearRegressionAnalysis
   ```

2. Start Jupyter:

   ```bash
   jupyter notebook
   ```

3. Open `Cars4U.ipynb` and run the cells from top to bottom.


## Project Status

This is an exploratory data analysis and baseline modeling project. It is best used as a portfolio-style analysis notebook and a foundation for further predictive modeling work.
