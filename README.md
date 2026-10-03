# Placement Readiness Predictor

This is a small machine learning project where I used student placement data to predict whether a student is **Placed** or **Not Placed**.

I made this project as part of the GDG AI/ML task to understand the basic machine learning workflow and get hands-on experience with classification models.

## Objective

The main goal of this project is to use different student-related features and build classification models that can predict the placement outcome.

## Dataset

The dataset used in this project was provided as synthetic placement data.

It contains information about students such as:

* CGPA
* Backlogs
* Number of projects
* Technical skill
* Communication skill
* Aptitude skill
* Teamwork skill
* Certifications
* Internship
* Training
* Placement status

The target variable is:

* `1` → Placed
* `0` → Not Placed

## Features I Used

I selected these 10 features because I felt they cover different parts of a student's placement profile:

* **CGPA** – academic performance
* **Backlogs** – academic consistency
* **Projects** – practical experience
* **Technical Skill** – technical ability
* **Communication Skill** – communication ability
* **Aptitude Skill** – aptitude/problem-solving ability
* **Teamwork Skill** – teamwork ability
* **Certifications** – additional learning
* **Internship** – practical industry exposure
* **Training** – additional preparation

## Data Preprocessing

Before training the models, I performed some basic preprocessing:

1. Converted the `backlogs` column into numeric values.
2. Converted the certification information into a binary value:

   * Missing → `0`
   * Present → `1`
3. Converted `Internship` into:

   * `Yes` → `1`
   * Other values → `0`
4. Converted `Training` into:

   * `Yes` → `1`
   * Other values → `0`
5. Converted the backlog information into a binary value where 0 or 1 backlog is treated as `1`.
6. Removed duplicate rows.
7. Split the data into training and testing sets using an 80/20 split.

## Models Used

I used two classification models in this project.

### 1. Logistic Regression

I used Logistic Regression as my first classification model.

It is useful for binary classification problems where there are two possible outputs.

### 2. Decision Tree

I used a Decision Tree as my second model.

I tested the Decision Tree using two different criteria:

* Gini Impurity
* Entropy

This helped me compare how the two criteria performed on the same dataset.

## Train-Test Split

I used an 80/20 train-test split.

* 80% of the data was used for training.
* 20% of the data was used for testing.

I used `random_state=2020` so that I could get the same split again when running the notebook.

I also used stratification to keep the class distribution similar in the training and testing data.

## Model Results

I evaluated the models using accuracy, precision, recall and F1-score.

| Model                   | Accuracy |
| ----------------------- | -------: |
| Logistic Regression     |      51% |
| Decision Tree - Gini    |      50% |
| Decision Tree - Entropy |    48.5% |

The models did not give very high accuracy and were around 50%.

I decided to keep these results as they were instead of changing the data just to get a higher accuracy. This also helped me understand that choosing a model alone does not guarantee good results. The relationship between the features and the target is also important.

The complete precision, recall and F1-score results can be seen in the notebooks.

## Example Prediction

I also tested the models with a sample student.

The sample had:

* CGPA: 8.5
* Backlogs: 0
* Projects: 6
* Technical Skill: 4
* Communication Skill: 4
* Aptitude Skill: 4
* Teamwork Skill: 4
* Certification: Yes
* Internship: Yes
* Training: Yes

The models predicted:

**Not Placed**

I used the same sample for the models so that their predictions could be compared using the same input.

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Google Colab
* GitHub

## What I Learned

While making this project, I learned how to:

* Select features for a classification problem
* Clean and preprocess data
* Convert categorical values into numerical values
* Create a binary target
* Remove duplicate rows
* Split data into training and testing sets
* Train Logistic Regression and Decision Tree models
* Use Gini and Entropy in Decision Trees
* Make predictions for new data
* Evaluate models using precision, recall and F1-score
* Understand that model performance depends on the data and features as well as the algorithm

## Future Improvements

If I continue working on this project, I would like to:

* Try more classification models
* Experiment with different preprocessing methods
* Tune the model parameters
* Explore more useful features from the dataset
* Add a simple interface where a user can enter student details
* Add feature importance or another way to explain the predictions

