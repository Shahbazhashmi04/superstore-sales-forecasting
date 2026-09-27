# Regional Sales Forecasting

A machine learning project that predicts sales bands for retail orders across four United States regions.

Built for the Artificial Intelligence course at Iqra University, Karachi, Fall 2024.

## What it does

Given the details of a retail order, such as region, product category, discount, quantity, and profit margin, the model predicts which sales band that order falls into: Low, Medium, High, or Very High.

## Dataset

USA Superstore dataset, 3,312 order records with 19 columns covering order dates, customer segment, product category, region, discount, profit, quantity, and sales.

## What I did

**Exploratory data analysis**
- Checked for missing values and duplicates (none found)
- Detected outliers using the interquartile range method across discount, profit, quantity, sales, and profit margin
- Plotted boxplots, histograms, and region counts

**Data cleaning**
- Dropped columns not useful for prediction (order id, customer, manufacturer, product name, zip, country)
- Removed 125 records with extreme negative profit margins below -1.0

**Preprocessing**
- StandardScaler for numerical features
- OneHotEncoder for categorical features
- Combined using ColumnTransformer inside a scikit-learn Pipeline

**Models compared**
| Model | Accuracy |
|---|---|
| **K Nearest Neighbors** | **81.2%** |
| Random Forest | 78.5% |
| Decision Tree | 77.4% |
| Naive Bayes | 31.7% |

K Nearest Neighbors performed best. Naive Bayes performed poorly, most likely because its independence assumption does not hold for these correlated retail features.

## Tech used

Python, scikit-learn, pandas, NumPy, Matplotlib, Seaborn, Google Colab

## How to run

Open the notebook in Google Colab or Jupyter, upload `superstore_dataset.csv` when prompted, and run the cells in order.
