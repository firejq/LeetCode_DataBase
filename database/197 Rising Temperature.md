## [197. Rising Temperature](https://leetcode.com/problems/rising-temperature) ##
```
# Write your MySQL query statement below
SELECT
	w1.Id
FROM
	Weather w1
INNER JOIN Weather w2 ON DATEDIFF(w1.Date, w2.Date) = 1
AND w1.Temperature > w2.Temperature;
```
- 使用 [`DATEDIFF(expr1, expr2)`](https://dev.mysql.com/doc/refman/5.7/en/date-and-time-functions.html#function_datediff "DATEDIFF") 函数
