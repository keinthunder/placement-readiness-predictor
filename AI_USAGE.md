# AI Usage

I took help from AI during different stages of this project, mainly to understand concepts, solve errors, and improve my understanding of the code.

Since I am still learning Machine Learning, AI was useful when I got confused about a concept or faced an error that I did not understand.

## How I Used AI

### Understanding Concepts

I took help from AI to understand some Machine Learning concepts in simple language, such as:

* Logistic Regression
* Sigmoid function
* Decision Trees
* Gini Impurity
* Entropy
* Binary Classification
* Train-test split
* Precision
* Recall
* F1-score

### Understanding My Code

I also took help from AI to understand parts of the code I was writing.

For example, I used it to understand:

* Selecting features using Pandas
* Converting categorical values into 0 and 1
* How `train_test_split()` works
* What `.fit()` does
* What `.predict()` does
* How `classification_report()` works
* Why feature names are needed when making a sample prediction

### Debugging

I took help from AI when I faced errors while working on the project.

Some of the problems included:

* Data type errors
* Syntax errors
* Problems with the target variable
* Errors when the target contained only one class
* Warnings caused by missing feature names during prediction

I tested the suggested solutions in Google Colab and checked the outputs myself.

### Understanding the Accuracy Change

I also took help from AI to understand why my accuracy was initially around 98% and later dropped to around 51%.

I understood that initially I was creating the target using conditions based on the same features that I was giving to the model. This meant I was defining the pattern between the features and target myself.

Later, I changed the target to use the actual `placement` column from the dataset:

```python id="7xqk1m"
y = (df["placement"] == "Placed").astype(int)
```

This made the model learn the relationship between the selected features and the actual placement outcome instead of using a pattern that I had already defined.

### Documentation

I also took help from AI while making the documentation for this project, including the README, decisions, and AI usage files.

I made sure that the documentation matched the work I actually did in my notebooks.

## My Contribution

I worked on the actual project implementation and made the final decisions about:

* Selecting the features
* Preprocessing the data
* Encoding categorical values
* Creating the target
* Choosing the models
* Training and testing the models
* Checking the results
* Making changes when something was not working
* Understanding the final code

AI was mainly used as a learning and debugging assistant while I worked on the project.

## Important Note

I did not blindly use AI-generated suggestions.

I tested the code in Google Colab, checked the outputs, and made changes based on what I understood.

Taking help from AI during this project helped me understand Machine Learning concepts better and solve problems that I faced while building the models.
