## 	[595	Big Countries ](https://leetcode.com/problems/big-countries)##
```
# Write your MySQL query statement below
SELECT
	NAME,
	population,
	area
FROM
	World
WHERE
	area > 3000000
OR population > 25000000;


```