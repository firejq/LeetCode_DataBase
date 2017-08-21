## [175	Combine Two Tables](https://leetcode.com/problems/combine-two-tables)   ##
```sql
# Write your MySQL query statement below.
SELECT
	FirstName,
	LastName,
	City,
	State
FROM
	Person
LEFT OUTER JOIN Address ON Person.PersonId = Address.PersonId;
```