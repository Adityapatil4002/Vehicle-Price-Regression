🚜 Predicting the Sale Price of Bulldozers using Machine Learning
In this notebook, we're going to go through an example machine learning project to use the characteristics of bulldozers and their past sales prices to predict the sale price of future bulldozers based on their characteristics.

Inputs: Bulldozer characteristics such as make year, base model, model series, state of sale (e.g. which US state was it sold in), drive system and more.
Outputs: Bulldozer sale price (in USD).
Since we're trying to predict a number, this kind of problem is known as a regression problem.

And since we're going to predicting results with a time component (predicting future sales based on past sales), this is also known as a time series or forecasting problem.

The data and evaluation metric we'll be using (root mean square log error or RMSLE) is from the Kaggle Bluebook for Bulldozers competition.

The techniques used in here have been inspired and adapted from the fast.ai machine learning course.

Overview
Since we already have a dataset, we'll approach the problem with the following machine learning modelling framework.

To work through these topics, we'll use pandas, Matplotlib and NumPy for data analysis, as well as, Scikit-Learn for machine learning and modelling tasks.

<img width="1055" height="562" alt="Screenshot 2025-09-17 160924" src="https://github.com/user-attachments/assets/69a9aa48-1f57-4eaa-b6a9-0603c6e82351" />

6 Step Machine Learning Framework
1. Problem Definition
For this dataset, the problem we're trying to solve, or better, the question we're trying to answer is,

How well can we predict the future sale price of a bulldozer, given its characteristics previous examples of how much similar bulldozers have been sold for?

2. Data
Looking at the dataset from Kaggle, you can you it's a time series problem. This means there's a time attribute to dataset.

In this case, it's historical sales data of bulldozers. Including things like, model type, size, sale date and more.

There are 3 datasets:

Train.csv - Historical bulldozer sales examples up to 2011 (close to 400,000 examples with 50+ different attributes, including SalePrice which is the target variable).
Valid.csv - Historical bulldozer sales examples from January 1 2012 to April 30 2012 (close to 12,000 examples with the same attributes as Train.csv).
Test.csv - Historical bulldozer sales examples from May 1 2012 to November 2012 (close to 12,000 examples but missing the SalePrice attribute, as this is what we'll be trying to predict).
Note: You can download the dataset bluebook-for-bulldozers dataset directly from Kaggle. Alternatively, you can also download it directly from the course GitHub.

3. Evaluation
For this problem, Kaggle has set the evaluation metric to being root mean squared log error (RMSLE). As with many regression evaluations, the goal will be to get this value as low as possible.

To see how well our model is doing, we'll calculate the RMSLE and then compare our results to others on the Kaggle leaderboard.

4. Features
Features are different parts of the data. During this step, you'll want to start finding out what you can about the data.

One of the most common ways to do this is to create a data dictionary.

For this dataset, Kaggle provides a data dictionary which contains information about what each attribute of the dataset means.

For example:

<img width="1143" height="611" alt="Screenshot 2025-09-17 161141" src="https://github.com/user-attachments/assets/adda2c75-d6ea-4788-b446-005387ba73b3" />
<img width="1118" height="727" alt="Screenshot 2025-09-17 161150" src="https://github.com/user-attachments/assets/2bb8513f-2225-4651-b418-2386cf978edc" />

...	...	...
SalePrice	cost of sale in USD	Target/dependent variable
You can download the full version of this file directly from the Kaggle competition page (account required) or view it on Google Sheets.
