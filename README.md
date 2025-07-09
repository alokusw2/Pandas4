# Pandas4

1 Problem 1 : Nth Highest Salary (https://leetcode.com/problems/nth-highest-salary/solution/)

Retrieve the n 
th
  highest salary from the Employee table. If there is no nth highest salary, we will return null.
------------------------------------------------
import pandas as pd

def nth_highest_salary(employee: pd.DataFrame, N: int) -> pd.DataFrame:
    unique_salaries = employee['salary'].drop_duplicates().sort_values(ascending=False).reset_index(drop=True)
    if N > len(unique_salaries):
        return pd.DataFrame({'Nth Highest Salary': [None]})
    else:
        return pd.DataFrame({'Nth Highest Salary': [unique_salaries.iloc[N-1]]})



------------------------------------------------

2 Problem 2 : Second Highest Salary ( https://leetcode.com/problems/second-highest-salary/ )

Write a solution to find the second highest distinct salary from the Employee table. If there is no second highest salary, return null (return None in Pandas).

The result format is in the following example.
------------------------------------------------
import pandas as pd

def second_highest_salary(employee: pd.DataFrame) -> pd.DataFrame:
    unique_salaries = employee['salary'].drop_duplicates().sort_values(ascending=False).reset_index(drop=True)
    if len(unique_salaries) < 2:
        return pd.DataFrame({'Second Highest Salary': [None]})
    else:
        return pd.DataFrame({'Second Highest Salary': [unique_salaries.iloc[1]]})



------------------------------------------------
