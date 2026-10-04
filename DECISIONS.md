# Project Decisions

This file contains some of the important decisions and changes I made while working on the project.

## 1. Correcting the Target Variable

At an earlier stage of the project, I got an accuracy of around 98%.

After checking my code, I realized that there was a problem with how I had created the target variable.

I changed it to:

```python
y = (df["placement"] == "Placed").astype(int)
```

This means:

* `Placed` → `1`
* Other values → `0`

After making this change, the accuracy dropped to around 51%.

Even though the accuracy became much lower, I kept this version because it correctly represents the placement outcome.

### Why I kept it

I did not want to change the target just to get a higher accuracy. This helped me understand that a high accuracy is not useful if the target or problem is not defined correctly.

---

## 2. Choosing Two Models

The task required me to use at least two classification models.

I chose:

* Logistic Regression
* Decision Tree

I chose Logistic Regression because it is a simple classification algorithm and was a good starting point for my first model.

I chose Decision Tree as the second model so I could try a different type of classification approach.

For the Decision Tree, I also tried both:

* Gini
* Entropy

## 3. Choosing the Features

I used 10 features:

* CGPA
* Backlogs
* Projects
* Technical Skill
* Communication Skill
* Aptitude Skill
* Teamwork Skill
* Certifications
* Internship
* Training

I selected these because they cover different areas of a student's profile, such as academics, skills, projects and additional preparation.

I also used the same features for both models so that the comparison would be fair.

---

## 4. Handling Categorical Values

Some columns in the dataset contained values such as `Yes` or missing values.

Machine learning models need numerical input, so I converted these values into `0` and `1`.

For example:

* Internship `Yes` → `1`
* Training `Yes` → `1`
* Certification present → `1`
* Certification missing → `0`

This made the data easier for the models to use.

---

## 5. Removing Duplicate Rows

I also removed duplicate rows before splitting the data.

I did this because I did not want the same records to appear multiple times in the dataset.

I used:

```python
data = data.drop_duplicates()
```

After this, I used the cleaned data for training and testing.
