##	596	Classes More Than 5 Students ##
```
# Write your MySQL query statement below
SELECT
	class
FROM
	courses
GROUP BY
	class
HAVING
	COUNT(DISTINCT student) >= 5;
```
- `WHERE` 子句用于筛选行记录，筛选分组要使用 `HAVING` 子句；