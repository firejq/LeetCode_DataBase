## 177	Nth Highest Salary    ##
```
CREATE FUNCTION getNthHighestSalary (N INT) RETURNS INT
BEGIN

DECLARE oset INT;
SET oset = N - 1;

RETURN (
	# Write your MySQL query statement below.
	SELECT
		IFNULL(
			(
				SELECT DISTINCT
					Salary
				FROM
					Employee
				ORDER BY
					Salary DESC
				LIMIT oset, 1
			),
			NULL
		)
);


END
```
limit后不能直接写N-1，因为limit后面不能接表达式；