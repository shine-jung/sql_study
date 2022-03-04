<!-- [프로그래머스] SQL 고득점 Kit - SELECT 풀이 (MySQL) by 정석민 -->

SELECT
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17042)

---

> 모든 레코드 조회하기

```
SELECT *
FROM ANIMAL_INS
ORDER BY ANIMAL_ID;
```

```
💡 SELECT

SELECT column_name(s)
FROM table_name

📝 SELECT * 는 전체 필드를 보여줍니다.
```

> 역순 정렬하기

```
SELECT NAME, DATETIME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID DESC;
```

```
💡 ORDER BY

오름차순 - ASC (생략할 수 있습니다)
내림차순 - DESC
```

> 아픈 동물 찾기

```
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION = 'Sick'
ORDER BY ANIMAL_ID;
```

```
💡 WHERE

WHERE column_name operator value
```

> 어린 동물 찾기

```
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION != 'Aged'
ORDER BY ANIMAL_ID;
```

> 동물의 아이디와 이름

```
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID;
```

> 여러 기준으로 정렬하기

```
SELECT ANIMAL_ID, NAME, DATETIME
FROM ANIMAL_INS
ORDER BY NAME, DATETIME DESC;
```

```
📝 콤마(,)로 구분하여 여러 기준으로 정렬할 수 있습니다.
```

> 상위 n개 레코드

```
SELECT NAME
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1;
```

```
💡 LIMIT

LIMIT 보여줄 행의 개수
```

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp)

<br>

_댓글 환영합니다!_
