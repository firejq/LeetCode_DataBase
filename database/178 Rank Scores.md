## 178	Rank Scores ##
方法一：
```
# Write your MySQL query statement below
SELECT
	Score,
	(
		SELECT
			count(*)
		FROM
			(
				SELECT DISTINCT
					Score
				FROM
					Scores
			) tmp
		WHERE
			tmp.Score >= Score
	) As Rank
FROM
	Scores
ORDER BY
	Score DESC
```
- 对每一个Score，找出>=它的score的数量，这个数量就是Rank；


方法二：
```
# Write your MySQL query statement below
SELECT
	Scores.Score AS Score,
	COUNT(*) AS Rank
FROM
	Scores
JOIN (
	SELECT DISTINCT
		Score
	FROM
		Scores
) Ranking ON Scores.Score <= Ranking.Score
GROUP BY
	Scores.Id
ORDER BY
	Scores.Score DESC;
```

- 求得每个Score与大于等于该Score的内连接表，再按照id分组，统计即可；