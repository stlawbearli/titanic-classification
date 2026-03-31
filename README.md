# titanic-classification
Binary classification project predicting Titanic passenger survival. Includes feature engineering (title-based age imputation), model comparison (Random Forest, KNN, Logistic Regression), cross-validation, and Kaggle submission. Best public score: 0.78708.

# README
# Titanic Survival Prediction

## Overview
Binary classification project predicting passenger survival on the Titanic.
Built as part of my Specialist Diploma in Data Science (AI) at Singapore Polytechnic.

**Best Kaggle Public Score: 0.78708 (Random Forest Classifier)**

---

## Dataset
- Source: [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic)
- Training set: 891 passengers
- Test set: 418 passengers

---

## Approach

### 1. Exploratory Data Analysis
- Visualised missing values using bar charts and heatmaps
- Identified key missing columns: Age (177), Cabin (687), Embarked (2)

### 2. Feature Engineering
- Extracted passenger titles (Mr, Mrs, Miss, Master) from names
- Used title-based median age imputation instead of overall median
  - Master: 3.5, Miss: 21.0, Mr: 30.0, Mrs: 35.0

### 3. Data Preprocessing
- Filled missing Embarked values with mode
- Dropped low-signal columns: Name, Ticket, Cabin, SibSp, Parch
- Encoded categorical variables (Sex, Embarked) using LabelEncoder

### 4. Models Trained
| Model | Accuracy |
|---|---|
| Random Forest | 82% |
| Logistic Regression | 80% |
| K-Nearest Neighbours (KNN) | 79% |

### 5. Cross-Validation
- 5-fold cross-validation on Random Forest
- Mean CV Score: 0.79

---

## Key Findings
- **Sex** was the strongest predictor of survival
- **Passenger class (Pclass)** showed an unexpected importance in the Random Forest model, likely acting as a proxy for ticketing sequences or family groupings, highlighting the nuances of administrative metadata in dataset analysis.
- Fare and PassengerId had minimal predictive value

---

## Files
| File | Description |
|---|---|
| `Titanic_Dataset_THR_Version 2.ipynb` | Primary Submission: Updated pipeline with Pandas 3.0 compliance and refined feature analysis. |
|`Titanic_Dataset_THR.ipynb` | Original main notebook for reference. |
| `rfdraft_titanic_predictions.csv` | Final Kaggle submission file |

---

## Tools & Libraries
- Python, Pandas, NumPy
- scikit-learn (RandomForestClassifier, KNeighborsClassifier, LogisticRegression)
- Matplotlib, Seaborn

---

## Author
**Tan Han Rong**
Specialist Diploma in Data Science (AI), Singapore Polytechnic

---

---
## Project Updates (March 2026)
To align with industry standards for the **Research & Engagement Specialist** technical assessment:
* **Modernized Pipeline:** Refactored data transformation logic to comply with Pandas 3.0 standards (replacing `inplace` operations with explicit assignment) to ensure data integrity.
* **Refined Feature Selection:** Re-included `PassengerId` after feature importance analysis revealed it as a significant proxy variable.
* **Report Optimization:** Suppressed library-level deprecation warnings to provide a cleaner, more "stakeholder-ready" notebook presentation.
