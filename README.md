# 🫀 AI-Based Stroke Risk Prediction and Analysis System

A comprehensive web-based healthcare application that predicts stroke risk by seamlessly combining structural machine learning data analysis with an interactive user interface. The system evaluates 15+ clinical measurements and lifestyle parameters to return real-time risk scores alongside actionable, personalized lifestyle recommendations.

---

## 🌟 Key Application Features
* **Comprehensive Health Mapping:** Evaluates a deep profile across demographic, clinical, historical, and behavioral inputs.
* **High-Accuracy ML Model Backend:** Powered by a Random Forest Classifier achieving a final model testing accuracy of **91.68%**.
* **Responsive Web User Interface:** A clean, serverless browser interface built using custom web elements (HTML/CSS/JS).
* **Instant Evaluation & Personalization:** Instantly calculates risk percentages and classifies the output into actionable risk levels with specialized advice.

---

## 📋 Input Feature Variables & Dataset Profile

The underlying predictive pipeline processes the following system variables collected from the structural dataset:

### 1. Demographic & Clinical Parameters
* **Age:** Continuous integer value (Highly weighted baseline indicator).
* **Gender / Marital Status:** Categorical parameters encoded for model compliance.
* **Average Glucose Level (mg/dL):** Quantitative metric indicating metabolic baselines.
* **Body Mass Index (BMI - kg/m²):** Cleaned using median imputation during baseline data profiling.

### 2. Behavioral Lifestyle Profiles
* **Smoking Profiles:** Categorized across statuses (`formerly smoked`, `never smoked`, `smokes`, `Unknown`).
* **Work Typing / Environments:** Classified indicators (`Private`, `Self-employed`, `Govt_job`, `children`, `Never_worked`).
* **Residence Types:** Categorical mapping across environmental categories (`Urban`, `Rural`).

### 3. Medical History Indicators
* **Hypertension / Heart Disease / Diabetes:** Boolean risk flags tracking chronic history indicators.

---

## 🧠 Machine Learning Engine Architecture

### 🛠️ Data Preprocessing & Pipeline Workflow
1. **Handling Missing Metadata:** Replaced missing structural null points within the `bmi` feature map using the calculated median of the feature array to prevent target data skewing.
2. **Encoding Transform:** Executed category dummy variable mapping (`pd.get_dummies`) dropping individual zero flags (`drop_first=True`) to handle non-numeric categorical feature values efficiently.
3. **Handling Imbalanced Targets (SMOTE):** The clinical database showcased extreme target label balance disparities (highly dominant non-stroke classes). Synthetic Minority Over-sampling Technique (SMOTE) was introduced to systematically synthesize missing class representations, balancing the baseline training distribution to **7,800 uniform target samples**.
4. **Data Fragmentation Split:** Divided the analytical pipeline down a split ratio framework consisting of **80% training models** and **20% validation models**.

### 📊 Performance & Statistical Results
* **Core Classifier:** Optimized Random Forest Classifier algorithm (`n_estimators=100`).
* **Final Model Verification Accuracy:** **91.68%**.

