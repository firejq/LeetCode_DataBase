## 182. Duplicate Emails ##
方式一：
```
# Write your MySQL query statement below
SELECT
	Email
FROM
	Person
GROUP BY
	Email
HAVING
	count(Email) > 1
```

方式二：
```
# Write your MySQL query statement below
SELECT DISTINCT
	a.Email
FROM
	Person AS a
INNER JOIN Person AS b ON a.Id != b.Id
AND a.Email = b.Email;
```