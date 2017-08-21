## 627	Swap Salary ##
```
# Write your MySQL query statement below
UPDATE salary
SET
    sex = CASE sex
        WHEN 'm' THEN 'f'
        ELSE 'm'
    END;
```
- 使用 [`CASE WHEN`](https://dev.mysql.com/doc/refman/5.7/en/control-flow-functions.html#operator_case) 流程控制