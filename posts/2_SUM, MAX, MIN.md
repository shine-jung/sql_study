<!-- [프로그래머스] SQL 고득점 Kit - SUM, MAX, MIN 풀이 (MySQL) by 정석민 -->

SUM, MAX, MIN
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17043)

---

> 최댓값 구하기

```
SELECT MAX(DATETIME) AS 시간
FROM ANIMAL_INS;
```

> 최솟값 구하기

```
SELECT MIN(DATETIME) AS 시간
FROM ANIMAL_INS;
```

> 동물 수 구하기

```
SELECT COUNT(*) AS count
FROM ANIMAL_INS;
```

```
📝 COUNT

COUNT(*) - 테이블 전체 행의 개수
COUNT(column_name) - 특정 Column의 데이터 개수 (NULL은 세지 않습니다)
```

> 중복 제거하기

```
SELECT COUNT(DISTINCT NAME) AS count
FROM ANIMAL_INS;
```

```
💡 DISTINCT - 중복을 제거하고 고유한 값만 반환합니다.
```

이 외의 집계함수로는 SUM, AVG이 있습니다.

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp)

<br>

_댓글 환영합니다!_
