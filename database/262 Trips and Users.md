## [262. Trips and Users](https://leetcode.com/problems/trips-and-users) ##
```
# Write your MySQL query statement below
SELECT
	t.Request_at AS `Day`,
	ROUND(
		SUM(IF (t.Status = 'completed', 0, 1)) / COUNT(*), 2
	) AS `Cancellation Rate`
FROM
	Trips t
INNER JOIN Users u ON t.Client_Id = u.Users_Id
WHERE
	t.Request_at BETWEEN '2013-10-01'
AND '2013-10-03'
AND u.Banned = 'No'
AND u.Role = 'client'
GROUP BY
	t.Request_at
ORDER BY
	t.Request_at;
```

 - 先筛选出符合条件的 trip 记录，然后按日期进行分组，再分别计算各组的 Cancellation Rate；
 - 计算 Cancellation Rate 时，使用 [`IF(expr1,expr2,expr3)`](https://dev.mysql.com/doc/refman/5.7/en/control-flow-functions.html#function_if) 函数、`ROUND()` 函数、`sum()` 函数；