<!-- [프로그래머스] SQL 고득점 Kit - IS NULL 풀이 (MySQL) by 정석민 -->

IS NULL
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17045)

---

> 이름이 없는 동물의 아이디

```
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE NAME IS NULL
ORDER BY ANIMAL_ID;
```

> 이름이 있는 동물의 아이디

```
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE NAME IS NOT NULL
ORDER BY ANIMAL_ID;
```

> NULL 처리하기

```
SELECT ANIMAL_TYPE, IFNULL(NAME, 'No name') AS NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS
ORDER BY ANIMAL_ID;
```

```
💡 IFNULL

IFNULL(column_name, 'NULL일 경우 대체할 값')
```

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp)

<br>

_댓글 환영합니다!_
