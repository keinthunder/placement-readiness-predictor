# Placement Readiness Predictor

A small Machine Learning project that predicts whether a student is **Placed** or **Not Placed** using placement-related student data.

This project was built as part of my **GDG AI/ML task** to understand the complete Machine Learning workflow — from data preprocessing and feature selection to training, prediction, and model evaluation.

## 🎯 Objective

The main objective of this project is to build a **binary classification system** that learns from student placement data and predicts the placement outcome of a student.

The target variable is:

* `1` → Placed
* `0` → Not Placed

## 📊 Dataset

The project uses the **synthetic placement dataset provided as part of the GDG task**.

The dataset contains student-related academic, skill, and career-preparation information.

### Features Used

| Feature          | Description                                     |
| ---------------- | ----------------------------------------------- |
| `cgpa`           | Student's CGPA                                  |
| `backlogs`       | Number of backlogs                              |
| `projects`       | Number of projects                              |
| `tech_skill`     | Technical skill score                           |
| `comm_skill`     | Communication skill score                       |
| `apt_skill`      | Aptitude skill score                            |
| `team_skill`     | Teamwork skill score                            |
| `certifications` | Whether the student has certifications          |
| `internship`     | Whether the student has completed an internship |
| `training`       | Whether the student has completed training      |

### Target

`placement`

* `Placed` → `1`
* Other placement status → `0`

## 🧹 Data Preprocessing

Before training the models, I performed some basic preprocessing:

* Converted the `backlogs` column into numeric values.
* Converted certification information into binary values:

  * Certification present → `1`
  * Missing certification → `0`
* Encoded internship:

  * `Yes` → `1`
  * Other values → `0`
* Encoded training:

  * `Yes` → `1`
  * Other values → `0`
* Converted the backlog information into a simple binary feature:

  * `0 or 1 backlog` → `1`
  * More than 1 backlog → `0`
* Removed duplicate rows.
* Split the dataset into training and testing data using an **80:20 ratio**.
* Used stratification during the train-test split to maintain the class distribution.

## 🤖 Machine Learning Models

I compared two simple classification approaches.

### 1. Logistic Regression

Logistic Regression was used as a simple baseline classification model.

It predicts the probability of a student belonging to one of the two classes and then classifies the student as **Placed** or **Not Placed**.

Notebook:

`placement_predictor_logisticregression.ipynb`

### 2. Decision Tree

A Decision Tree was used to learn classification rules from the selected features.

I also compared two splitting criteria:

* **Gini Impurity**
* **Entropy**

Notebook:

`Placement_pre_
