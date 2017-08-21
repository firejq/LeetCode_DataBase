## 183. Customers Who Never Order ##
```
# Write your MySQL query statement below
SELECT
	Customers. NAME AS 'Customers'
FROM
	Customers
WHERE
	Customers.Id NOT IN (
		SELECT DISTINCT
			CustomerId
		FROM
			Orders
	);
```