# 🍷 Wine Quality Prediction using Machine Learning*
A complete machine learning pipeline for predicting Portuguese redwine quality using classical ML, clustering, dimentioanl reduction, imbalance handling, and model selction.

THis project presents a full data science worklow that performs:
- Exploratory data analysis
- Visualization and correlation inspection
- Clustering using K-Means + PCA
- Handling of class imbalance using SMOTE(Synthetic Minority Over-sampling Technique)
- Training and evaluation of multiple ML classifiers
- Selection of the best-performing model
- Deployment-ready prediction pipeline
# 📊 Dataset
- Source Professor Paulo COrtez, University of Minho
- Samples: 1599 wines
- Features: 11 physicochemical attributes
- Target: Quality - converted to binary classification (Good or Bad)

| Class | Meaning              |
| ----- | -------------------- |
| 0     | Bad / Medium quality |
| 1     | Good quality (≥ 7)   |
* We set 7 as a threshold value to classify Good and Bad, we can set any number to classify
# 🧠 Pipeline Architecture
``` text 
Raw Dataset
     │
     ▼
Exploratory Data Analysis & Visualization
     │
     ▼
Standard Scaling
     │
     ▼
K-Means Clustering + PCA Visualization
     │
     ▼
Binary Class Conversion (Good / Bad)
     │
     ▼
SMOTE Class Balancing
     │
     ▼
Feature Scaling
     │
     ▼
PCA Dimensionality Reduction (90% variance)
     │
     ▼
Model Training & Evaluation
     │
     ▼
Best Model Selection (Random Forest)
     │
     ▼
Model Saving & New Data Prediction
```
# 📈 Models Implemented
| Model               | Accuracy | Precision | Recall | F1-Score |
|--------------------|----------|-----------|--------|----------|
| Logistic Regression| 0.74     | 0.71      | 0.69   | 0.70     |
| K-Nearest Neighbors| 0.81     | 0.79      | 0.77   | 0.78     |
| Support Vector Mach| 0.84     | 0.83      | 0.81   | 0.82     |
| Random Forest      | 0.89     | 0.88      | 0.86   | 0.87     |

                  
   ✔ Random Forest was selected as the final deployed model
 -** Wine quality is not linear, and its variables are chemically dependent. PCA collapses these nonlinear relations into linear eigenvectors, The pipeline over-compresed because we are working on three distructive operations :**
- SMOTE
- StandardScaler
- PCA (0.90)
  but when we remove the PCA from the Pipeline we got the following : around 91% accuracy on Random Forest 


  

# ⚖ Handling Imbalanced Data 
The dataset is highly imbalanced.
To avoid misleading accuracy, SMOTE (Synthetic Minority Oversampling Technique) is applied:
| Before SMOTE        | After SMOTE          |
| ------------------- | -------------------- |
| 1382 bad / 217 good | 1105 bad / 1105 good |

  ✔ This significantly improves precision, recall, and F1 score reliability.

# 🧮 Dimensionality Reduction

PCA retains 90% o the original variance using 7 principal components, improving 
- Training speed
- Generalization
- Noise robustness

  🔍 Example Prediction
``` text  new_data = {
 'fixed acidity':7.3,
 'volatile acidity':0.65,
 'citric acid':0.00,
 'residual sugar':1.2,
 'chlorides':0.065,
 'free sulfur dioxide':15,
 'total sulfur dioxide':21,
 'density':0.9946,
 'pH':3.39,
 'sulphates':0.47,
 'alcohol':10
}
```
# Output:
``` text
  Good Quality Wine
```

# 🎯 Learning Outcomes

This project demonstrates:
- Data preprocessing & feature engineering
- Visualization & clustering
- Imbalanced data handling
- Model evaluation beyond accuracy
- Real ML deployment workflow











