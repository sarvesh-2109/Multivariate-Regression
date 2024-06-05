# Multivariate Regression

This project demonstrates the implementation of a multivariate linear regression model to predict salaries based on candidates' experience, test scores, and interview scores.

## Output


https://github.com/sarvesh-2109/Multivariate-Regression/assets/113255836/435193e2-9c97-48d9-8c09-67893d8a3f94



## Overview

In this project, we use a dataset containing information on candidates' experience, test scores, interview scores, and their corresponding salaries. Our goal is to build a regression model that can predict a candidate's salary based on the provided features.

## Dataset

The dataset (`hiring.csv`) includes the following columns:
- `experience`: Years of experience (can be in words)
- `test_score(out of 10)`: Score obtained in a test (out of 10)
- `interview_score(out of 10)`: Score obtained in the interview (out of 10)
- `salary($)`: Salary in dollars

## Steps to Run the Project

1. **Importing Libraries:**
   - pandas
   - numpy
   - scikit-learn (linear_model)
   - word2number (w2n)
   - math
   - warnings

2. **Reading the CSV File:**
   ```python
   data = pd.read_csv('/content/hiring.csv')
   ```

3. **Data Preprocessing:**
   - Fill missing experience values with 'zero'.
   - Convert experience from words to numbers.
   - Fill missing test scores with the median test score.

4. **Training the Regression Model:**
   ```python
   reg = linear_model.LinearRegression()
   reg.fit(data[['experience', 'test_score(out of 10)', 'interview_score(out of 10)']], data['salary($)'])
   ```

5. **Predictions:**
   - Predicting salary for an employee with 2 years of experience, 9 test score, and 6 interview score.
   - Predicting salary for an employee with 12 years of experience, 10 test score, and 10 interview score.

## Results

- The coefficients of the regression model:
  ```python
  reg.coef_
  ```

- The intercept of the regression model:
  ```python
  reg.intercept_
  ```

- Predicted salary for 2 years of experience, 9 test score, 6 interview score:
  ```python
  first_prediction = reg.predict([[2, 9, 6]])
  ```

- Predicted salary for 12 years of experience, 10 test score, 10 interview score:
  ```python
  second_prediction = reg.predict([[12, 10, 10]])
  ```

## Example Predictions

- For an employee with 2 years of experience, 9 test score, and 6 interview score:
  ```
  The predicted salary is: $53713.87
  ```

- For an employee with 12 years of experience, 10 test score, and 10 interview score:
  ```
  The predicted salary is: $93747.80
  ```

## Repository Structure

- `Multivariate_Regression.ipynb`: The Jupyter notebook containing the code for the project.
- `hiring.csv`: The dataset used for training and predictions.

## Conclusion

This project provides a practical example of how to apply multivariate linear regression for predicting outcomes based on multiple features. The steps include data preprocessing, model training, and making predictions, which are essential skills for data analysis and machine learning tasks.
