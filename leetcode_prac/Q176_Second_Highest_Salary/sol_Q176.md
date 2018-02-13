## Answer of Q175 - Second Highest Salary
The answer is simply as below:
```
SELECT 
  MAX(Salary) AS "SecondHighestSalary"
FROM 
  Employee
WHERE 
  SALARY < (SELECT MAX(Salary) FROM Employee)
```

Another solution:
```
SELECT 
  Salary AS "SecondHighestSalary"
FROM 
  Employee
ORDER BY Salary DESC LIMIT 1 OFFSET 1
```
