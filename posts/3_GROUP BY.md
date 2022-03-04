<!-- [프로그래머스] SQL 고득점 Kit - GROUP BY 풀이 (MySQL) by 정석민 -->

GROUP BY
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17044)

---

> 고양이와 개는 몇 마리 있을까

```
SELECT ANIMAL_TYPE, COUNT(*) AS count
FROM ANIMAL_INS
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE;
```

```
💡 GROUP BY

GROUP BY는 값이 같은 행을 요약 행으로 그룹화합니다.
주로 COUNT(), SUM()와 같은 집계함수와 함께 사용됩니다.
```

> 동명 동물 수 찾기

```
SELECT NAME, COUNT(*) AS COUNT
FROM ANIMAL_INS
GROUP BY NAME
HAVING COUNT(NAME) > 1
ORDER BY NAME;
```

```
📝 WHERE와 HAVING의 차이

두 문법은 비슷하게 보일 수 있지만, WHERE는 각 행을 필터링하는 데 사용되고,
HAVING은 그룹화 이후, 요약 행을 필터링하는 데 사용됩니다.
```

> 입양 시각 구하기(1)

```
SELECT HOUR(DATETIME), COUNT(HOUR(DATETIME)) AS COUNT
FROM ANIMAL_OUTS
WHERE HOUR(DATETIME) >= 9 AND HOUR(DATETIME) < 20
GROUP BY HOUR(DATETIME)
ORDER BY HOUR(DATETIME);
```

```
📝 날짜 및 시간 데이터 형식에서 일부만 추출하기

HOUR()는 날짜 및 시간 데이터 형식에서 시간을 추출합니다.
연도, 월, 일, 분, 초 또한 함수를 통해 추출할 수 있습니다.
```

```
📝 문법 작성 순서

SELECT ▶️ FROM ▶️ WHERE ▶️ GROUP BY ▶️ HAVING ▶️ ORDER BY 순으로 작성합니다.
```

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp)

<br>

_댓글 환영합니다!_
