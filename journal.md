# Purpose of chosing this dataset 
- Easy to understand and beginner friendly
- Factors that I can understand and relate to
- Small quick project to understand and appreciate ML basics

# Things I'll learn
- EDA
- Feature types and targets
- Train/Test split baselines
- Metrics:
    - Accuracy
    - Confusion Matrix
    - MAE/RMSE
- Liner Models:
    - Logistic/Linear regression
    - interpretability via cofficients

# Opening Quetions
I have some doubts before starting:
- What is EDA?
- What is confusion Matrix?
- What is MAE/RMSE?
- Are linear and logistic two types of regression?

# Answer from Perplexity

## What is EDA?

EDA = Exploratory Data Analysis.
It’s the phase where you look at the data with summary stats and plots to understand distributions, spot patterns, and detect issues before modeling.

For you, that means:

Checking ranges of sleep duration, stress, etc.

Visualizing how sleep quality changes with stress, activity, disorders.

### What exactly is modelling??
In this context, modeling is the step where you build a mathematical “rule” from data so it can make predictions on new, unseen cases.

More concretely for your sleep project:
    - You start with examples: each row has features (age, stress, activity, sleep duration, etc.) and a target (e.g., has a sleep disorder, or sleep quality score).
    - You choose an algorithm (e.g., logistic regression, linear regression).
    - You let the algorithm learn parameters from the data so that its outputs match the targets as well as possible (minimize error on the training set).
    - The result of this learning is a model: a function that takes inputs (a person’s lifestyle features) and outputs a prediction (probability of a disorder, or a quality score).

So:
    - “Doing EDA” = understanding the data.
    - “Doing modeling” = training and evaluating one or more models (linear/logistic, trees, etc.) to map inputs → outputs, then checking how well they generalize to new data.

## What is a confusion matrix?

A confusion matrix is a table that compares what your classifier predicted vs the true labels, broken down by class.

For a binary problem (e.g., “has sleep disorder” vs “no disorder”), it counts:

    - True Positives (TP): model says “disorder” and it’s correct.
    - False Positives (FP): model says “disorder” but actually none.
    - False Negatives (FN): model says “no disorder” but there is one.
    - True Negatives (TN): model says “no disorder” and it’s correct.

This helps you see not just accuracy, but where the model gets confused (e.g., missing people with insomnia).

## What are MAE and RMSE?

Both are error metrics for regression (continuous targets like sleep quality).

- MAE (Mean Absolute Error):
    - Average of ∣prediction−true∣.
    - “On average, how many points off am I?”

- RMSE (Root Mean Squared Error):
    - Square errors, average them, then take the square root.
    - Penalizes large errors more than MAE.

## Are linear and logistic two types of regression?

es, they’re both regression models, but used for different tasks.

- Linear regression
    - Output: continuous number (e.g., predict sleep quality 1–10).
    - Fits a straight line (or hyperplane) to minimize squared error.

- Logistic regression
    - Output: probability of a class (e.g., having a sleep disorder).
    - Used for classification, with a sigmoid to squash outputs to [0,1].

So they share the “regression” name and some math, but in practice you’ll treat one as your basic regressor and the other as your basic classifier.

# Understand the data with EDA (60–75 min)

## Load and inspect 

Tool details:
- describe()
- value_counts()

## What is IQR??

IQR is the **Interquartile Range** – it measures how spread out the **middle 50%** of your data is. 
- You take the 25th percentile (Q1) and the 75th percentile (Q3).  
- \( \text{IQR} = Q3 - Q1 \).  
- Example with your sleep duration:
  - Q1 ≈ 6.4 hours, Q3 ≈ 7.8 hours → IQR ≈ 1.4 hours, meaning the central half of people sleep within a 1.4‑hour band.

### Inspire me with some interesting observations.
    - The dataset contains 374 adults (27–59 years) with average sleep duration ≈7.1 hours and sleep quality ≈7/10.
    - Participants are moderately active (~6.8k steps/day, ~1 hour activity), with mid‑level stress (~5.4/10).
    - Most have normal or slightly elevated BMI, and about 40% of records include a tagged sleep disorder (insomnia or sleep apnea), while the rest are unlabeled and likely represent no disorder.
    - Nurses are the most common occupation, suggesting interesting analyses around shift work and sleep outcomes.

## Univariate analysis

## Bivariate analysis
