# BigMart Sales Analysis

## 📌 Project Overview
BigMart Sales Analysis is an exploratory and predictive modeling project focused on understanding sales patterns across various stores and products. The dataset includes store-specific and product-specific attributes, which help in predicting future sales.

## 📂 Repository Structure
```
BigMart-Sales-Analysis/
├── data/                      # Dataset folder
│   ├── dataset.csv
├── notebooks/                 # Jupyter Notebooks
│   ├── final/                 # Final analysis notebook
│   │   ├── BigMart_Sales_Final.ipynb
│   ├── experiments/           # Experimental trials and explorations
│   │   ├── trial_1.ipynb
│   │   ├── trial_2.ipynb
│   │   ├── ...
├── scripts/                   # Python scripts for preprocessing & modeling
│   ├── preprocess.py
│   ├── train_model.py
│   └── ...
├── submission/                # Model submissions
│   ├── experiments/           # Experimental submission trials
│   │   ├── submission_trial_1.csv
│   │   ├── submission_trial_2.csv
│   │   ├── ...
│   ├── submission_final.csv  # From final notebook
├── approach.pdf                # Explanation of approach (currently empty)
├── LICENSE                     # License information
├── README.md                   # Project description
├── requirements.txt             # Dependencies
├── .gitignore                   # To ignore unnecessary files
```

## 💊 Dataset Information
The dataset consists of store-level and product-level attributes that influence sales. Below are the key features:

### Train File: CSV containing item-outlet information with sales value
| Variable | Description |
|----------|-------------|
| `Item_Identifier` | Unique product ID |
| `Item_Weight` | Weight of product |
| `Item_Fat_Content` | Whether the product is low fat or not |
| `Item_Visibility` | The % of total display area of all products in a store allocated to the particular product |
| `Item_Type` | The category to which the product belongs |
| `Item_MRP` | Maximum Retail Price (list price) of the product |
| `Outlet_Identifier` | Unique store ID |
| `Outlet_Establishment_Year` | The year in which store was established |
| `Outlet_Size` | The size of the store in terms of ground area covered |
| `Outlet_Location_Type` | The type of city in which the store is located |
| `Outlet_Type` | Whether the outlet is just a grocery store or some sort of supermarket |
| `Item_Outlet_Sales` | Sales of the product in the particular store. This is the outcome variable to be predicted. |

## 🛠️ Steps in Analysis
1. **Exploratory Data Analysis (EDA)** –
   - Understanding data distribution, checking for missing values, and detecting outliers.
   - Visualizing relationships between variables using plots and correlation matrices.
   - Identifying trends and patterns in sales data.
2. **Feature Engineering** –
   - Handling missing values through imputation strategies.
   - Encoding categorical variables using target encoding for `Outlet_Identifier`.
   - Creating new features that can improve model performance, such as age of the store.
   - Scaling numerical features if necessary.
3. **Model Building** –
   - Using **LightGBM**, which does not require additional encoding for other categorical variables.
   - Training models on the dataset and fine-tuning hyperparameters.
   - Implementing cross-validation to ensure model generalization.
4. **Evaluation & Interpretation** –
   - Assessing model performance using metrics such as RMSE, R², and MAE.
   - Interpreting model coefficients and feature importance to understand key sales drivers.
   - Comparing different models to identify the best-performing approach.

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/BigMart-Sales-Analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the Jupyter notebook and run the analysis:
   ```bash
   jupyter notebook notebooks/final/BigMart_Sales_Final.ipynb
   ```

## 📈 Sample Results
### **Sales Distribution Insights**
- The sales data follows a right-skewed distribution, with most products having lower sales values.
- Supermarkets tend to have higher average sales compared to grocery stores.

### **Feature Importance (LightGBM)**
- `Item_MRP` is the most influential feature in predicting sales.
- `Outlet_Type` and `Outlet_Location_Type` also play significant roles in sales variation.

### **Correlation Matrix**
- Strong correlation observed between `Item_MRP` and `Item_Outlet_Sales`.
- `Item_Visibility` has a weak correlation with sales, indicating it may not be a strong predictor.

### **Model Performance**
| Model | RMSE | R² |
|--------|--------|--------|
| LightGBM | **1080.5** | **0.71** |
| Random Forest | 1150.2 | 0.68 |
| Linear Regression | 1350.9 | 0.60 |

The **LightGBM model** outperformed others with the lowest RMSE and highest R² value, making it the best choice for our final submission.

---
🔹 **Author:** Netra Kulkarni  
🔹 **GitHub:** https://uniquenetra.github.io/  
🔹 **Contact:** uniquenetra@gmail.com

