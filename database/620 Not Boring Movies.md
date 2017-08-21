##[ 620	Not Boring Movies](https://leetcode.com/problems/not-boring-movies) ##
```
# Write your MySQL query statement below
SELECT
	*
FROM
	cinema
WHERE
	MOD (id, 2) != 0
AND description != 'boring'
ORDER BY
	rating DESC;
```