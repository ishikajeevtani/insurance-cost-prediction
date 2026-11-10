
# 🏥 Insurance Cost Prediction: Data Cleaning & Feature Engineering

A machine learning project that takes a raw medical insurance dataset and turns it into clean, model-ready data. The end goal is to predict **individual insurance charges** from personal details like age, BMI, smoking status and region.

This notebook covers the foundation of every ML project: **EDA → Data Cleaning → Feature Engineering → Feature Selection.**

---

## 📊 Dataset

| Column | Description |
|---|---|
| `age` | Age of the person |
| `sex` | Male / Female |
| `bmi` | Body Mass Index |
| `children` | Number of dependents |
| `smoker` | Smoker or not |
| `region` | Residential region (northeast, northwest, southeast, southwest) |
| `charges` | Insurance charges billed (**target variable**) |

---

## 🔄 Workflow

### 1. Exploratory Data Analysis (EDA)
- Checked shape, data types, summary statistics and missing values
- Histograms with KDE for `age`, `bmi`, `children`, `charges`
- Count plots for `children`, `sex`, `smoker`
- Box plots to spot outliers
- Correlation heatmap

### 2. Data Cleaning & Processing
- Removed duplicate rows
- Verified there are no null values
- Encoded `sex` → `is_female` (0/1) and `smoker` → `is_smoker` (0/1)
- One-hot encoded `region` (`drop_first=True` to avoid redundancy)

### 3. Feature Engineering
- Created **BMI categories**: Underweight, Normal, Overweight, Obese
- One-hot encoded the BMI categories
- Standardized `age`, `bmi` and `children` using `StandardScaler`

### 4. Feature Selection
- **Pearson correlation** of every feature with `charges`
- **Chi-square test** (α = 0.05) between each categorical feature and charge quartiles
- Kept only the features that showed a statistically meaningful relationship

---

## ✅ Final Feature Set

```
age, is_female, bmi, children, is_smoker, region_southwest, bmi_category_Obese
```
Target: `charges`

---

## 💡 Key Insights

- 🚬 **Smoking status** has the strongest relationship with insurance charges
- ⚖️ **Obesity** (BMI category) also pushes charges up noticeably
- 📈 **Age** shows a clear positive relationship with charges
- 🗺️ Region and sex have a much weaker effect than the features above

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C8CBF?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)

---

## 📁 Project Structure

```
insurance-cost-prediction/
│
├── insurance.ipynb     # Full EDA, cleaning and feature engineering notebook
├── insurance.csv       # Dataset
└── README.md
```

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/ishikajeevtani/insurance-cost-prediction.git
cd insurance-cost-prediction

# 2. Install dependencies
pip install numpy pandas seaborn matplotlib scikit-learn scipy jupyter

# 3. Open the notebook
jupyter notebook insurance.ipynb
```

---

## 🚀 Next Steps

- Train regression models (Linear Regression, Random Forest, XGBoost)
- Evaluate with R², MAE and RMSE
- Tune hyperparameters and compare model performance

---

## 👩‍💻 Author

**Ishika Jeevtani**
B.Tech CSE | Machine Learning & AI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ishika-jeevtani)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/ishikajeevtani)

⭐ If you found this useful, consider giving the repo a star!
