## [181	Employees Earning More Than Their Managers](https://leetcode.com/problems/employees-earning-more-than-their-managers)    ##
```
# Write your MySQL query statement below
SELECT
	a.`Name` AS Employee
FROM
	Employee AS a
INNER JOIN Employee AS b ON a.ManagerId = b.Id
AND a.Salary > b.Salary;
```