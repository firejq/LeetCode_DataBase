## [	185	Department Top Three Salaries](https://leetcode.com/problems/department-top-three-salaries)    ##
```
# Write your MySQL query statement below
SELECT
	d. NAME AS 'Department',
	e1. NAME AS 'Employee',
	e1.Salary
FROM
	Employee e1
INNER JOIN Department d ON e1.DepartmentId = d.Id
WHERE
	(
		SELECT
			COUNT(DISTINCT e2.Salary)
		FROM
			Employee e2
		WHERE
			e2.Salary > e1.Salary
		AND e1.DepartmentId = e2.DepartmentId
	) < 3
ORDER BY
	Department;
```

- 工资前三名的员工，可理解为：在该部门中比这三名员工中任一位工资高的人不超过3人，据此便可作为WHERE条件，加上 DepartmentId 连接，便可找出一个 Department 中工资前三的员工记录，最后再与 Department 表内连接，列出部门名称即可；
