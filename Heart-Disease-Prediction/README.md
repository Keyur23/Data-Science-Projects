# Heart Disease Prediction Using Machine Learning

## 📋 Introduction

Predicting and diagnosing heart disease is one of the biggest challenges in the medical industry and relies on factors such as physical examination, symptoms, and signs of the patient. Heart disease is recognized as the world's deadliest disease, where the heart is unable to pump the required amount of blood to the remaining organs of the human body to perform regular functions.

This project uses **Machine Learning** techniques to predict heart disease based on various medical attributes, helping reduce the death rate of heart patients through early detection and diagnosis.

## 🎯 Problem Statement

Factors that influence heart disease include:
- Body cholesterol levels
- Smoking habits and obesity
- Family history of illnesses
- Blood pressure
- Work environment
- Age, gender, and heart rate

By leveraging machine learning algorithms combined with data analysis, we can predict heart disease with high accuracy based on these symptoms and features, enabling better medical decision-making.

## 📊 Dataset

The dataset (`heart.csv`) contains **303 records** with **14 attributes**:

### Features Description:

| Feature | Description | Values/Range |
|---------|-------------|--------------|
| **age** | Age of the patient | Years |
| **sex** | Gender of the patient | 1 = Male, 0 = Female |
| **cp** | Chest pain type | 0-3 (Different types of chest pain) |
| **trestbps** | Resting blood pressure | mm Hg |
| **chol** | Serum cholesterol | mg/dl |
| **fbs** | Fasting blood sugar (glucose) | 1 = > 120 mg/dl glucose, 0 = ≤ 120 mg/dl glucose |
| **restecg** | Resting electrocardiographic results | 0-2 |
| **thalach** | Maximum heart rate achieved | BPM (beats per minute) |
| **exang** | Exercise induced angina | 1 = Yes, 0 = No |
| **oldpeak** | ST depression induced by exercise | Numeric value |
| **slope** | Slope of peak exercise ST segment | 0-2 |
| **ca** | Number of major vessels colored by fluoroscopy | 0-3 |
| **thal** | Thalassemia | 0 = Unknown, 1 = Normal, 2 = Fixed defect, 3 = Reversible defect |
| **target** | Heart disease presence | 1 = Disease, 0 = No Disease |

## 🔬 Project Workflow

### 1. **Data Loading and Initial Exploration**
- Load the heart disease dataset using pandas
- Display initial rows to understand data structure
- Check for data types and missing values

### 2. **Exploratory Data Analysis (EDA)**
- Statistical summary of the dataset
- Distribution analysis of features
- Correlation analysis to identify relationships between features
- Visualization of feature correlations with the target variable

### 3. **Data Preprocessing**
- **Feature Scaling**: Applied `StandardScaler` to normalize continuous features (age, trestbps, chol, thalach, oldpeak)
- **Encoding**: Applied one-hot encoding to categorical variables
- **Train-Test Split**: Split data into 70% training and 30% testing sets

### 4. **Model Training**
- Algorithm: **Logistic Regression**
- Solver: `liblinear`
- Training on preprocessed data

### 5. **Model Evaluation**
- Accuracy Score
- Confusion Matrix
- Classification Report (Precision, Recall, F1-Score)

## 🛠️ Technologies and Libraries Used

**Core Libraries:**
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computations
- **matplotlib** - Data visualization
- **seaborn** - Statistical data visualization
- **scikit-learn** - Machine learning algorithms and tools

### Key Scikit-learn Modules:
- `LogisticRegression` - Classification algorithm
- `StandardScaler` - Feature normalization
- `train_test_split` - Data splitting
- `accuracy_score`, `confusion_matrix`, `classification_report` - Model evaluation

## 📈 Model Performance

### Logistic Regression Results:

| Metric | Training Set | Testing Set |
|--------|--------------|-------------|
| **Accuracy** | 86.79% | 86.81% |

#### Test Set Classification Report:
```
              Precision    Recall    F1-Score    Support
No Disease        0.87      0.83       0.85         41
Disease           0.87      0.90       0.88         50
Accuracy                               0.87         91
```

#### Confusion Matrix (Test Set):
```
                Predicted
              No Disease  Disease
Actual
No Disease        34         7
Disease            5        45
```

### Key Insights:
- The model achieved **86.81% accuracy** on unseen test data
- High precision and recall for both classes (disease and no disease)
- Minimal overfitting (training and testing accuracies are very close)
- The model correctly identified 45 out of 50 disease cases (90% recall for disease class)

## 🚀 How to Run the Project

### Prerequisites:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Steps:
1. **Clone the repository** (if not already done):
   ```bash
   git clone https://github.com/Keyur23/Data-Science-Projects.git
   cd Data-Science-Projects/Heart-Disease-Prediction
   ```

2. **Ensure the dataset is present**:
   - The `heart.csv` file should be in the same directory

3. **Open the Jupyter Notebook**:
   ```bash
   jupyter notebook main.ipynb
   ```

4. **Run the cells sequentially**:
   - Execute each cell in order to reproduce the analysis
   - Modify the dataset path in the data loading section if needed

### Important Note:
Update the file path in the notebook's data loading section to use a relative path:
```python
# Change the hardcoded path to a relative path:
df = pd.read_csv("heart.csv")
```

## 📊 Key Visualizations

The project includes several important visualizations:

1. **Correlation Heatmap**: Shows relationships between all features
2. **Feature Correlation with Target**: Bar plot showing which features have the strongest correlation with heart disease
3. **Statistical Distribution**: Summary statistics for all numerical features

## 🔍 Features with Strongest Correlation to Heart Disease

Based on the correlation analysis in the notebook:
- **cp** (Chest pain type)
- **thalach** (Maximum heart rate achieved)
- **slope** (Slope of peak exercise ST segment)
- **exang** (Exercise induced angina)
- **oldpeak** (ST depression)

These features play a crucial role in predicting heart disease presence.

## 💡 Future Improvements

Potential enhancements for this project:

1. **Try Additional Algorithms**:
   - Random Forest Classifier
   - Support Vector Machine (SVM)
   - K-Nearest Neighbors (KNN)
   - Neural Networks
   - Gradient Boosting (XGBoost, LightGBM)

2. **Hyperparameter Tuning**:
   - Use GridSearchCV or RandomizedSearchCV for optimal parameters

3. **Feature Engineering**:
   - Create interaction features
   - Apply feature selection techniques

4. **Cross-Validation**:
   - Implement k-fold cross-validation for more robust evaluation

5. **Deployment**:
   - Create a web interface using Flask or Streamlit
   - Deploy as an API for real-time predictions

6. **Handle Class Imbalance** (if any):
   - Apply SMOTE or other resampling techniques

## 📝 Conclusion

This project successfully demonstrates how machine learning can be applied to predict heart disease with **86.81% accuracy** using Logistic Regression. The model shows balanced performance across both classes and can serve as a foundation for more advanced predictive systems in healthcare.

Early detection of heart disease through such predictive models can significantly help medical professionals in diagnosis and treatment planning, potentially saving lives.

## 👨‍💻 Author

**Keyur**

## 📄 License

This project is part of a data science portfolio and is available for educational purposes.

---

**Note**: This model is for educational and research purposes only. It should not be used as a substitute for professional medical advice, diagnosis, or treatment.
