## Answer of Q177 - Nth Highest Salary (medium)

My initial answer was wrong (forgot to add "DISTINCT" to avoid the "no-answer-case"). The accepted solution is as below:
```
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN 
  # define offset number
  DECLARE offnum INT;
  SET offnum = N-1;
  RETURN (

    SELECT 
      DISTINCT Salary
    FROM
      Employee ORDER BY Salary DESC LIMIT 1 OFFSET offnum

);
END
```
