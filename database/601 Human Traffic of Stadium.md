## 601 Human Traffic of Stadium ##
```
# Write your MySQL query statement below
SELECT DISTINCT
	t1.*
FROM
	stadium t1,
	stadium t2,
	stadium t3
WHERE
	t1.people >= 100
AND t2.people >= 100
AND t3.people >= 100
AND (
	(
		t3.id - t2.id = 1
		AND t2.id - t1.id = 1
		AND t3.id - t1.id = 2
	) -- id: t1 < t2 < t3
	OR (
		t2.id - t1.id = 1
		AND t2.id - t3.id = 2
		AND t1.id - t3.id = 1
	) -- id: t3 < t1 < t2
	OR (
		t1.id - t2.id = 1
		AND t1.id - t3.id = 2
		AND t2.id - t3.id = 1
	) -- id: t3 < t2 < t1
)
ORDER BY
	t1.id;
```
自联结查询
由于需要列出匹配的所有记录，因此此处的t1需能匹配到第一天、第二天、第三天……直到连续最后一天的所有情况；
若 `SELECT DISTINCT t1.*` 中的 `t1` 替换成 `tx`，则 WHERE 子句中的条件需要相应地做出改变；
类似题目（简单）：[180. Consecutive Numbers](https://leetcode.com/problems/consecutive-numbers/description/)