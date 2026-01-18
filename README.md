# 🎯📈 Customer Segmentation and Subscriber Churn Prediction

## 📌 Project Overview

This project analyzes customer behavior for a **video streaming platform** with two main goals:

1. **Customer segmentation** – identify distinct user groups based on demographics and subscription behavior.
2. **Subscriber churn prediction** – understand and quantify which factors are associated with users cancelling their subscription via testing machine learning models.

The analysis combines **exploratory data analysis (EDA)**, **churn-focused aggregations**, **segmentation logic**, and **machine learning models** to generate actionable insights that could be used by product, marketing, or retention teams.

> Note: The dataset is composed of mock data for a fictional company. It was generated using Le Chat's generative AI model.


## 🧠 Key Questions
<b><i> Segmentation </b></i>
* How does churn vary by **age group**, **subscription status**, and **cluster**?
* Are there identifiable customer segments with systematically higher churn?
* Which groups should be prioritized for retention efforts?

<b><i> Machine Learning </b></i>
* Which dataset features are the most important to predict churn likelihood?
* What is the churn probability for different age groups and engagement behaviours?
* Which model is best to use for predicting subscriber churn to balance accuracy with interpretability?


## 📊 Dataset Description

The dataset represents users of a video streaming platform and includes:

* **Demographics**: age groups
* **Engagement metrics**: engagement frequency and time
* **Behavioral / derived features**: cluster assignments
* **Target variable**: subscribed vs. churned


## 🔍 Methodology

### 1. Exploratory Data Analysis (EDA)

* Distribution of subscribers across age groups
* Overall churn rate
* Churn comparison by subscription status
* Grouped percentage calculations to normalize comparisons
* * Churn rates are calculated:

  * overall
  * by age group
  * by cluster
  * by cluster × age group × subscription status
* Emphasis is placed on **within-group normalization** (percentages summing to 100 per cluster)

### 2. Customer Segmentation

* Customers are grouped into **clusters** using K-Means clustering based on engagement patterns
* Cluster composition is analyzed by:

  * age group
  * subscription status
* Percentages are computed **within each cluster** to allow fair comparison

### 3. Churn Prediction Model
Different machine learning models are trained, tested and tuned to find the best model for the data: 
* Logistic Regression
* Decision Tree
* Random Forest
  
Once the most accurate model is selected:
* The most important risk factors for customer churn are identified
* The probability that each customer churns is extracted
* The model is deployed to predict whether new customers will churn based on their engagement characteristics and age group


## 🛠 Tech Stack

**Python**
 * pandas (Data manipulation & transformation)
 * scikit-learn (Machine learning models & evaluation)
 * seaborn (Data visualization)


## 📈 Key Insights

* Segementation reveals that customers with both low engagement frequency and low engagement time are at the highest churn risk
  * Thresholds of engagement time below 7.5 minutes and engagement frequency below 10 define this group
  * Targeted or automated marketing campaigns should be focused on customers that fall under these engagement thresholds
* Churn behavior varies meaningfully across age groups, with customers over 35 exhibiting the highest churn risk
* The Random Forest model performed the best on predicting subscriber churn, achieving an F1 score/accuracy of 94%
* Engagement frequency contributes the most to the machine learning model's churn prediction, indicating that this characteristic may be the most important when monitoring subscriber engagement behaviour for churn risk

These insights can inform:

* targeted retention campaigns
* automation strategies
* pricing or plan adjustments
* personalized product recommendations

## 📁 Project Structure

```
├── data
  ├── AZWatch_subscribers.csv
├── notebook.ipynb        # Main analysis notebook
├── README.md             # Project documentation
```

## 🚀 How to Use

1. Clone the repository
2. Open `notebook.ipynb` in Jupyter
3. Run cells top-to-bottom to reproduce the analysis

## 🔮 Future Improvements

* Integrate time-based features (tenure, recency)
* Package the analysis into reusable functions or a pipeline

