# California House Price Prediction: Regression Analysis

## Project Overview
This project evaluates several supervised learning regression techniques by applying them to the **California Housing dataset**. The goal is to predict the median house price in various California districts based on features like median income, house age, and location.

## Dataset
The project uses the **California Housing dataset** fetched via `sklearn.datasets`.
* **Size:** 20,640 records, 8 features.
* **Target Variable:** `MedHouseValue` (Median house value for California districts, expressed in hundreds of thousands of dollars).
* **Features:** Median Income, House Age, Average Rooms, Average Bedrooms, Population, Average Occupancy, Latitude, and Longitude.

## Methodology

### 1. Preprocessing & Exploration
* **Data Cleaning:** Verified that the dataset contains **zero missing values** across all 20,640 records.
* **Data Splitting:** Divided the data into training (80%) and testing (20%) sets.

### 2. Regression Models Implemented
I implemented and compared five different regression algorithms:
1.  **Linear Regression:** Fits a linear equation to the observed data.
2.  **Decision Tree Regressor:** Uses a tree-like model of decisions to predict values.
3.  **Random Forest Regressor:** An ensemble of decision trees that improves accuracy and controls overfitting.
4.  **Gradient Boosting Regressor:** Sequentially builds trees to correct errors made by previous ones.
5.  **Support Vector Regressor (SVR):** Finds a hyperplane in a high-dimensional space that best fits the data.

## Performance Comparison
The models were evaluated using Mean Absolute Error (MAE), Mean Squared Error (MSE), and the R-squared (R2) score.

| Model | MAE | MSE | R² Score |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | 0.533 | 0.529 | 0.596 |
| **Decision Tree** | 0.457 | 0.501 | 0.617 |
| **Random Forest** | 0.334 | 0.258 | 0.803 |
| **Gradient Boosting** | **0.373** | **0.291** | **0.778** |
| **SVR** | 0.859 | 1.332 | -0.016 |

> **Note:** Performance may vary slightly depending on the specific random seed used during splitting. In my final run, **Gradient Boosting** and **Random Forest** consistently led the rankings.

## Key Findings
* **Best Model:** **Gradient Boosting Regressor** (and Random Forest) performed the best, achieving an R2 score of approximately **79%**. These ensemble methods effectively captured the complex, non-linear relationships in the dataset.
* **Worst Model:** **SVR** was the worst-performing algorithm with an R2 score of **-0.016**, indicating that it failed to generalize to this specific dataset without further hyperparameter tuning.
* **Insights:** Tree-based ensemble models significantly outperformed basic linear methods, suggesting the housing price factors in California have strong non-linear interactions.

## How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/nikhilgopi/california-housing-regression.git](https://github.com/nikhilgopi/california-housing-regression.git)
    ```
2.  **Install requirements:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  **Open the notebook:**
    ```bash
    jupyter notebook HousePrice_Prediction_in_california_Regression.ipynb
    ```
