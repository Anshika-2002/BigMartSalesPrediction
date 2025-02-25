# BigMart Sales Prediction

## 📌 Project Overview
This project aims to predict sales of products in different BigMart outlets using machine learning. The **XGBoost Regressor** model is used to train and evaluate sales predictions based on various product and store attributes.

## 📂 Dataset Details
- **Total Rows:** 8,523
- **Total Features:** 12 (including target variable `Item_Outlet_Sales`)

| Feature | Description |
|---------|------------|
| **Item_Identifier** | Unique ID for each product. |
| **Item_Weight** | Weight of the product (missing values filled with mean). |
| **Item_Fat_Content** | Fat content (Low Fat / Regular) - standardized values. |
| **Item_Visibility** | Percentage visibility of the product in the store. |
| **Item_Type** | Category of the product (e.g., Dairy, Soft Drinks, Meat, etc.). |
| **Item_MRP** | Maximum Retail Price (MRP) of the product. |
| **Outlet_Identifier** | Unique ID for each store. |
| **Outlet_Establishment_Year** | Year when the store was established. |
| **Outlet_Size** | Store size (Small/Medium/Large) - missing values filled with mode. |
| **Outlet_Location_Type** | Tier of the location (Tier 1, Tier 2, Tier 3). |
| **Outlet_Type** | Type of outlet (Grocery Store, Supermarket Type1, Type2, Type3). |
| **Item_Outlet_Sales** | **Target Variable** - Sales of the product in the store. |

## 🛠️ Preprocessing Steps
- **Handling Missing Values:**
  - `Item_Weight`: Filled with mean.
  - `Outlet_Size`: Filled based on `Outlet_Type`.
- **Encoding Categorical Variables:**
  - Used `LabelEncoder()` for categorical columns.
  - Standardized `Item_Fat_Content` labels (e.g., `low fat`, `LF` → `Low Fat`).

## 📊 Exploratory Data Analysis (EDA)
- **Distribution Plots:**
  - `sns.displot()` used for numerical features.
- **Count Plots:**
  - `sns.countplot()` used for categorical features.

## 🚀 Model Training
- **Algorithm Used:** XGBoost Regressor
- **Data Split:**
  - `train_test_split(X, Y, test_size=0.2, random_state=2)`
  - `X`: All features except `Item_Outlet_Sales`
  - `Y`: `Item_Outlet_Sales`
- **Training the Model:**
  - `XGBRegressor()` fitted on `X_train, Y_train`

## 📈 Model Evaluation
- **Metric Used:** R² Score (`metrics.r2_score(Y_train, training_data_prediction)`).

## 📌 Key Takeaways
- **Proper preprocessing** (handling missing values, encoding categorical data) is crucial.
- **Feature engineering improves model performance.**
- **XGBoost is effective for structured regression tasks.**
- **Optimize hyperparameters to enhance accuracy.**

## 💻 Installation & Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/BigMart-Sales-Prediction.git
   cd BigMart-Sales-Prediction
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook for training and evaluation.



