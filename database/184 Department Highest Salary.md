## [184	Department Highest Salary](https://leetcode.com/problems/department-highest-salary)    ##

```
SELECT
	D.Name AS Department,
	E.Name AS Employee,
	E.Salary AS Salary
FROM
	Employee E
INNER JOIN Department D ON E.DepartmentId = D.Id
AND (E.DepartmentId, E.Salary) IN (
	SELECT
		DepartmentId,
		MAX(Salary) AS max
	FROM
		Employee
	GROUP BY
		DepartmentId
);
```
- 将Employee表按照DepartmentId分组，再将各组中Salary最高的对应Id和该Salary组成一个集合，即各Department中最高Salary的集合；
再逐一判断employee的id和Salary是否在该集合中即可；