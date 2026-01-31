# Going Abroad Prediction

A machine learning project that predicts the likelihood of students going abroad for higher education based on various academic and demographic features.

## 📋 Project Overview

This project uses machine learning algorithms to predict whether a student will successfully go abroad for studies (positive/negative outcome) based on multiple features including academic performance, test scores, costs, and demographic information.

## 🎯 Features

The model considers 19 features including:
- **Demographic Information**: Gender, Age
- **Academic Metrics**: Multiple numbered features (Feature_1 through Feature_17)
- **Standardized Test Scores**: GPA_IELTS_Feature, Top_Score
- **Performance Indicators**: Result_feature
- **Financial Aspects**: Cost_feature

## 📊 Dataset

- **Total Records**: 1,523 students
- **Features**: 19 input features
- **Target Variable**: `Abroad_result` (positive/negative)
- **Data Source**: [Going_Abroad_prediction.csv](https://raw.githubusercontent.com/SaddamHosen42/Going_Abroad_prediction/refs/heads/main/Going_Abroad_prediction.csv)

### Data Characteristics
- No missing values
- Mix of categorical and numerical features
- Balanced preprocessing applied

## 🛠️ Technologies Used

- **Python 3.x**
- **Libraries**:
  - `pandas` - Data manipulation and analysis
  - `scikit-learn` - Machine learning algorithms and preprocessing
  - `numpy` - Numerical computations

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/SaddamHosen42/Going_Abroad_prediction.git
cd Going_Abroad_prediction
