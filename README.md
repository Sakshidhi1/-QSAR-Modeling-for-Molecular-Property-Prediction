# 🧪 QSAR-Modeling-for-Molecular-Property-Prediction

This project involves building Quantitative Structure–Activity Relationship (QSAR) models to predict molecular properties based on chemical descriptors and fingerprints. The models were trained and evaluated using various techniques including Ridge Regression and XGBoost.

## 📂 Dataset

- Molecular descriptors and fingerprints
- Total samples: 12150
- Features: 7541 after combination of fingerprints and scaled descriptors

 ## ⚙️ Preprocessing

- *Scaling*: StandardScaler applied to descriptors
- *Combining*: Descriptors and fingerprints stacked horizontally
- *Dimensionality Reduction*: PCA used for Ridge Regression model
- *Train/Test Split*: 80/20

## 🧠 Models Compared

🔹 Ridge Regression (Linear)

Used after PCA to handle high-dimensional features

✅ Cross-Validation R²: 0.50 ± 0.01

✅ Test R²: 0.4855

✅ Test RMSE: 0.911

🔹 XGBoost Regressor (Non-Linear)

Non-linear gradient boosting model

⚠️ Cross-Validation R²: 0.43 ± 0.19 (higher variance)

✅ Test R²: 0.68

✅ Test RMSE: 0.56

📊 Model Comparison Summary

## Model	CV R² Score	Test R²	Test RMSE

Ridge + PCA	0.50 ± 0.01	0.4855	0.911
XGBoost	0.43 ± 0.19	0.68	0.56


> 🔎 Insight: While XGBoost performed better on the test set, it showed high variance in cross-validation. Ridge Regression was more stable, making it a safer generalization choice.


## 📈 Visualizations

📌 Residual Distribution (Ridge & XGBoost)

📌 Predicted vs. Actual Plot

📌 Feature Importance (XGBoost only)

## 🗂️ File Structure

📁 qsar-model/
├── egfr.csv
├── molecular_descriptors.csv
├── ridge_model.pkl
├── pca_transform.pkl
├── ridge_qsar.png
├── xgboost_qsar.png
├── QSAR_ML.ipynb
└── README.md


## 📦 Requirements

pip install rdkit scikit-learn pandas xgboost matplotlib seaborn


## ✅ Conclusion

Only Ridge Regression and XGBoost were compared.

Ridge provided stable and explainable results despite lower test R².

XGBoost, while more accurate on the test set, showed high variability and possible overfitting.

Future work can explore:

Ensembling both models

Feature selection

Additional regression methods like SVR or Random Forest
