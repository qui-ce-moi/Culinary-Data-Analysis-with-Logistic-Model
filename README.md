# Culinary-Data-Analysis-with-Logistic-Model
A machine learning project predicting high-traffic recipes on a food blog using nutritional data. Features Logistic Regression and Random Forest classifiers."
🍳 Recipe Site Traffic Prediction
A data science project that predicts whether a recipe will generate high traffic on a recipe website, using machine learning classification models.

Python Jupyter scikit-learn License: MIT

📌 Project Overview
Recipe websites need to decide which recipes to feature on their homepage to maximize site traffic. This project analyzes a dataset of 947 recipes with nutritional information (calories, carbohydrate, sugar, protein), recipe categories, and serving sizes to build a classification model that predicts whether a recipe will generate high traffic or not.

🎯 Objective
Business Goal: Predict high-traffic recipes to optimize homepage content and increase overall site engagement.
Technical Goal: Build and compare classification models (Logistic Regression vs. Random Forest) to achieve the best prediction accuracy.
📊 Dataset
The dataset (
recipe_site_traffic_2212.csv
) contains 947 recipes with the following features:

Feature	Description	Type
recipe	Unique recipe identifier	Integer
calories	Calorie count per serving	Float
carbohydrate	Carbohydrate content (g)	Float
sugar	Sugar content (g)	Float
protein	Protein content (g)	Float
category	Recipe category (e.g., Chicken, Breakfast, Beverages)	Categorical
servings	Number of servings	Integer
high_traffic	Target variable — High or Low traffic	Categorical
Key Statistics
10 recipe categories: Chicken, Breakfast, Beverages, Lunch/Snacks, Potato, Pork, Dessert, Vegetable, Meat, One Dish Meal
574 high-traffic vs. 373 low-traffic recipes (imbalanced classes)
Missing values present in nutritional columns (~52 rows)
🛠️ Methodology
1. Data Cleaning & Preprocessing
Merged Chicken Breast category into Chicken to reduce redundancy.
Cleaned the servings column by removing string artifacts (e.g., "4 as a snack" → 4).
Imputed missing nutritional values (calories, carbohydrate, sugar, protein) using category-wise median to preserve distribution within each food category.
Encoded the target variable: High → 1, otherwise → 0.
2. Exploratory Data Analysis (EDA)
Traffic Distribution: ~60.6% of recipes are high-traffic, ~39.4% are low-traffic.
Calorie Distribution: Right-skewed, with most recipes between 100–600 calories.
Category Analysis: Traffic patterns vary significantly across food categories.
Servings Breakdown: 4-serving recipes are the most common (41.2%).
3. Feature Engineering
Applied one-hot encoding to the category column.
Split data into 80% training and 20% testing sets with stratified sampling.
Applied StandardScaler normalization for the Logistic Regression model.
4. Model Building & Evaluation
Baseline Model — Logistic Regression
Metric	Low Traffic (0)	High Traffic (1)	Overall
Precision	0.69	0.85	—
Recall	0.79	0.77	—
F1-Score	0.74	0.81	—
Accuracy	—	—	0.78
Comparison Model — Random Forest
Metric	Low Traffic (0)	High Traffic (1)	Overall
Precision	0.61	0.79	—
Recall	0.72	0.70	—
F1-Score	0.66	0.75	—
Accuracy	—	—	0.71
🏆 Winner: Logistic Regression
Logistic Regression outperforms Random Forest across all metrics in this case, achieving 78% accuracy with a higher F1-score for both classes.

📂 Project Structure
Recipes_Data_Science/
│
├── Tarifler.ipynb                  # Main Jupyter Notebook (full analysis pipeline)
├── recipe_site_traffic_2212.csv    # Raw dataset
├── Data_Sample.xlsx                # Sample data reference
├── requirements.md                 # Python dependencies
├── .gitignore                      # Git ignore rules
└── README.md                       # Project documentation
🚀 Getting Started
Prerequisites
Python 3.10+
pip (Python package manager)
Installation
Clone the repository

bash
git clone https://github.com/<your-username>/Recipes_Data_Science.git
cd Recipes_Data_Science
Install dependencies

bash
pip install pandas numpy matplotlib seaborn scikit-learn
Run the notebook

bash
jupyter notebook Tarifler.ipynb
📈 Key Findings
Logistic Regression is the better model for this dataset, with 78% accuracy and a balanced F1-score across both classes.
Food category is a strong predictor — certain categories (e.g., Potato, Vegetable) tend to have higher traffic rates.
Nutritional values alone are not sufficient — combining them with category and serving information significantly improves prediction power.
The confusion matrix reveals 59 true negatives, 89 true positives, 16 false positives, and 26 false negatives — showing the model is slightly better at predicting high-traffic recipes.
🧰 Tech Stack
Tool	Purpose
Python 3.10	Programming language
Pandas	Data manipulation and analysis
NumPy	Numerical computations
Matplotlib	Static visualizations
Seaborn	Statistical data visualization
scikit-learn	Machine learning models and evaluation
Jupyter Notebook	Interactive development environment
📝 Future Improvements
 Hyperparameter tuning with GridSearchCV / RandomizedSearchCV
 Try additional models (XGBoost, SVM, Neural Networks)
 Feature importance analysis to identify the most impactful predictors
 Cross-validation for more robust performance estimation
 Deploy the model as a REST API for real-time predictions
🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

📄 License
This project is licensed under the MIT License — see the 
LICENSE
 file for details.

👤 Author
Emir C.

GitHub: @your-github-username
If you found this project helpful, please consider giving it a ⭐ star!


Comment
Ctrl+Alt+M
