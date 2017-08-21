## 176	Second Highest Salary    ##
```
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
			LIMIT 1 OFFSET 1
		),
		NULL
	) AS SecondHighestSalary;
```
- 使用了 [`IFNULL(expr1, expr2)`](https://dev.mysql.com/doc/refman/5.7/en/control-flow-functions.html#function_ifnull) 函数，将空值替换为NULL