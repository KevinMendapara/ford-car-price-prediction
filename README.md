# Ford Car Price Prediction

A machine learning project that predicts the selling price of Ford cars
using vehicle specifications such as model, year, transmission, mileage,
fuel type, tax, MPG, and engine size.

## Project Overview

This project performs exploratory data analysis (EDA), feature
preprocessing, and linear regression modeling on a Ford car dataset.

The notebook compares two preprocessing approaches:

1.  **One-hot encoding** for categorical variables.
2.  **Label encoding** for categorical variables.

Both approaches are followed by feature scaling and a Linear Regression
model. Model performance is evaluated using **R²** and **Adjusted R²**.

## Dataset

The dataset contains **17,966 records** and **9 columns**:

  Column           Description
  ---------------- ---------------------------------------
  `model`          Ford car model
  `year`           Manufacturing year
  `price`          Car selling price --- target variable
  `transmission`   Transmission type
  `mileage`        Vehicle mileage
  `fuelType`       Fuel type
  `tax`            Vehicle tax
  `mpg`            Miles per gallon
  `engineSize`     Engine size

The dataset contains no missing values according to the notebook's
null-value check.

## Exploratory Data Analysis

The notebook explores the target variable and relationships between
price and vehicle features using:

-   Price distribution histogram
-   Correlation heatmap
-   Price vs. year boxplot
-   Mileage vs. price scatterplot
-   Price vs. engine size boxplot
-   Price vs. transmission boxplot
-   Price vs. fuel type boxplot
-   Price vs. model boxplot
-   Price vs. tax boxplot
-   Price vs. MPG boxplot

## Data Preprocessing

### One-Hot Encoding

The categorical features:

-   `model`
-   `transmission`
-   `fuelType`

are converted using `pandas.get_dummies()` with `drop_first=True`.

The numerical features:

-   `year`
-   `mileage`
-   `mpg`
-   `engineSize`

are standardized using `StandardScaler`.

### Label Encoding

A second preprocessing approach uses `LabelEncoder` for:

-   `model`
-   `transmission`
-   `fuelType`

The notebook then applies `StandardScaler` to the resulting feature
columns.

## Model

The project uses:

**Linear Regression** from Scikit-learn.

The data is split into training and testing sets using:

-   Test size: **33%**
-   Random state: **42**

## Results

### One-Hot Encoding + Linear Regression

-   R²: **0.8397**
-   Adjusted R²: **0.8387**

### Label Encoding + Linear Regression

-   R²: **0.7310**
-   Adjusted R²: **0.7307**

Based on the notebook results, the **one-hot encoding approach performs
better** than the label encoding approach for this dataset.

## Technologies Used

-   Python
-   NumPy
-   Pandas
-   Matplotlib
-   Seaborn
-   Scikit-learn
-   Jupyter Notebook

## Project Structure

``` text
.
├── Ford Car Price prediction .ipynb
├── ford.csv
└── README.md
```

## How to Run

1.  Clone this repository.
2.  Make sure `ford.csv` is in the same directory as the notebook.
3.  Install the required Python libraries:

``` bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

4.  Open the notebook:

``` bash
jupyter notebook
```

5.  Run the cells in **Ford Car Price prediction .ipynb**.

## Future Improvements

Possible improvements to this project include:

-   Comparing additional regression algorithms such as Random Forest,
    Gradient Boosting, or XGBoost.
-   Using cross-validation for more reliable model evaluation.
-   Performing systematic hyperparameter tuning.
-   Handling categorical variables with preprocessing pipelines.
-   Investigating potential outliers and unusual values in the dataset.
-   Adding residual/error analysis.
-   Building a simple web application for interactive price prediction.

## Conclusion

This project demonstrates an end-to-end machine learning workflow for
Ford car price prediction, from data exploration and preprocessing to
model training and evaluation. The notebook's results show that the
**one-hot encoded Linear Regression model achieves the stronger
performance**, with an R² of approximately **0.84**.

