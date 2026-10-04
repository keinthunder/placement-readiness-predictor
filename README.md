# Placement Readiness Predictor

A Machine Learning project that predicts whether a student is **Placed** or **Not Placed** using placement-related student data.

This project was built as part of my **GDG AI/ML task** to understand the complete Machine Learning workflow.

## 🎯 Objective

The goal is to build a **binary classification model** that learns from student placement data.

**Target:**

* `1` → Placed
* `0` → Not Placed

## 📊 Dataset

The project uses the **synthetic placement dataset provided for the GDG task**.

### Features Used

* CGPA
* Backlogs
* Projects
* Technical skill
* Communication skill
* Aptitude skill
* Teamwork skill
* Certifications
* Internship
* Training

These features were selected because they represent different parts of a student's academic performance, skills, and placement preparation.

## 🧹 Preprocessing

The following preprocessing steps were performed:

* Converted `backlogs` to numeric values.
* Certifications: present → `1`, missing → `0`.
* Internship: `Yes` → `1`, otherwise → `0`.
* Training: `Yes` → `1`, otherwise → `0`.
* Backlogs: `0 or 1` → `1`, otherwise → `0`.
* Removed duplicate rows.
* Split the data into **80% training and 20% testing** data.
* Used stratification during the split.

## 🤖 Models

### 1. Logistic Regression

Used as a simple baseline classification model.

Notebook: `placement_predictor_logisticregression.ipynb`

### 2. Decision Tree

Used to learn classification rules from the selected features.

Two criteria were tested:

* Gini
* Entropy

Notebook: `Placement_predictor_decisiontree.ipynb`

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Decision Tree (Gini) | 50% | 0.50 | 0.50 | 0.50 |
| Decision Tree (Entropy) | **55%** | **0.54** | **0.55** | **0.54** |
| Logistic Regression | 51% | 0.49 | 0.51 | 0.47 |

## 🔍 Example Prediction

A sample student with:

* CGPA: `8.5`
* Backlogs: `0`
* Projects: `6`
* Skill scores: `4`
* Certification: `Yes`
* Internship: `Yes`
* Training: `Yes`

was given to the models.

The prediction was:

**Not Placed**

## 💡 Important Learning

Initially, I created the target using conditions based on the same features given to the model. This produced around **98% accuracy** because I was essentially defining the pattern myself.

I corrected this by using the actual placement column:

```python
y = (df["placement"] == "Placed").astype(int)
```

After this correction, the accuracy became around 50%.

This taught me that the target variable must represent the actual problem instead of being created from assumptions.

More details are available in `DECISIONS.md`.

## 🛠️ Technologies

* Python
* Pandas
* Scikit-learn
* Google Colab
* GitHub

## 📁 Project Structure

```text
placement-readiness-predictor/
│
├── placement_readiness_synthetic_10000.csv
├── placement_predictor_logisticregression.ipynb
├── Placement_predictor_decisiontree.ipynb
├── README.md
├── DECISIONS.md
└── AI_USAGE.md
```

The dataset was provided as part of the GDG task.

## 📚 What I Learned

* Data preprocessing
* Feature selection
* Categorical encoding
* Train-test splitting
* Logistic Regression
* Decision Trees
* Model evaluation
* Precision, recall and F1-score
* Debugging Machine Learning code
* Understanding model results

## 🚀 Future Improvements

* Try more classification algorithms.
* Perform hyperparameter tuning.
* Use cross-validation.
* Analyze feature importance.
* Build a simple input interface.

## 👨‍💻 Author

**Shashank Verma**

B.Tech — Artificial Intelligence & Machine Learning

Built for the **GDG AI/ML task**.
