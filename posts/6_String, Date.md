<!-- [프로그래머스] SQL 고득점 Kit - String, Date 풀이 (MySQL) by 정석민 -->

String, Date
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17047)

---

> 루시와 엘라 찾기

```
SELECT ANIMAL_ID, NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS
WHERE NAME IN ('Lucy', 'Ella', 'Pickle', 'Rogan', 'Sabrina', 'Mitty')
ORDER BY ANIMAL_ID;
```

```
💡 IN

IN 연산자를 사용하면 WHERE 절에서 여러 값을 선택할 수 있습니다.
OR 연산자와 같은 역할을 합니다.
```

> 이름에 el이 들어가는 동물 찾기

```
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE NAME LIKE '%el%'
AND ANIMAL_TYPE = 'Dog'
ORDER BY NAME;
```

```
📝 LIKE에서 대소문자 구분이 이루어지지 않습니다.
```

> 중성화 여부 파악하기

```
SELECT ANIMAL_ID, NAME, IF(SEX_UPON_INTAKE LIKE 'Intact%', 'X', 'O') AS '중성화'
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```

```
💡 IF(condition, 참일 때 반환 값, 거짓일 때 반환 값)
```

> 오랜 기간 보호한 동물(2)

```
SELECT INS.ANIMAL_ID, INS.NAME
FROM ANIMAL_INS AS INS
JOIN ANIMAL_OUTS AS OUTS
ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
ORDER BY OUTS.DATETIME - INS.DATETIME DESC
LIMIT 2;
```

```
📝 DATEDIFF를 이용해도 됩니다.
```

> DATETIME에서 DATE로 형 변환

```
SELECT ANIMAL_ID, NAME, DATE_FORMAT(DATETIME, '%Y-%m-%d') AS 날짜
FROM ANIMAL_INS
ORDER BY ANIMAL_ID;
```

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp)

<br>

_댓글 환영합니다!_
