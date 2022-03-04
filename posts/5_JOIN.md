<!-- [프로그래머스] SQL 고득점 Kit - JOIN 풀이 (MySQL) by 정석민 -->

JOIN
--
[문제집 링크](https://programmers.co.kr/learn/courses/30/parts/17046)

---

> 없어진 기록 찾기

```
SELECT OUTS.ANIMAL_ID, OUTS.NAME
FROM ANIMAL_OUTS AS OUTS
LEFT JOIN ANIMAL_INS AS INS
ON OUTS.ANIMAL_ID = INS.ANIMAL_ID
WHERE INS.ANIMAL_ID IS NULL
ORDER BY OUTS.ANIMAL_ID;
```

```
💡 JOIN

아래 이미지는 JOIN의 사용법을 쉽게 이해할 수 있는 자료입니다.
해당 문제는 두 집합의 차집합을 구하는 문제였습니다.
왼쪽 가운데의 코드를 참고하여 해결하였습니다.
```

![](https://images.velog.io/images/shinejung/post/14e540e3-741c-4089-8b11-485bf70371fe/b12d8a7e66ac9ff6dce9345229d6edce.jpeg)

> 있었는데요 없었습니다

```
SELECT INS.ANIMAL_ID AS ANIMAL_ID, INS.NAME AS NAME
FROM ANIMAL_INS AS INS
JOIN ANIMAL_OUTS AS OUTS
ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
WHERE OUTS.DATETIME < INS.DATETIME
ORDER BY INS.DATETIME;
```

```
📝 JOIN -> INNER JOIN
```

> 오랜 기간 보호한 동물(1)

```
SELECT INS.NAME AS NAME, INS.DATETIME AS DATETIME
FROM ANIMAL_INS AS INS
LEFT JOIN ANIMAL_OUTS AS OUTS
ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
WHERE OUTS.ANIMAL_ID IS NULL
ORDER BY INS.DATETIME
LIMIT 3;
```

> 보호소에서 중성화한 동물

```
SELECT
    INS.ANIMAL_ID AS ANIMAL_ID,
    INS.ANIMAL_TYPE AS ANIMAL_TYPE,
    INS.NAME AS NAME
FROM ANIMAL_INS AS INS
JOIN ANIMAL_OUTS AS OUTS
ON INS.ANIMAL_ID = OUTS.ANIMAL_ID
WHERE INS.SEX_UPON_INTAKE LIKE 'Intact%'
AND (OUTS.SEX_UPON_OUTCOME LIKE 'Spayed%' OR OUTS.SEX_UPON_OUTCOME LIKE 'Neutered%')
ORDER BY INS.ANIMAL_ID;
```

```
📝 더 간단한 WHERE문

WHERE INS.SEX_UPON_INTAKE != OUTS.SEX_UPON_OUTCOME
```

```
💡 LIKE

LIKE는 WHERE 절에서 문자열의 패턴을 검색하는 데 사용됩니다.
```
📖 LIKE의 자세한 사용법은 [여기](https://www.w3schools.com/sql/sql_like.asp)서 확인 할 수 있습니다.

<br>

Source : [www.w3schools.com](https://www.w3schools.com/sql/sql_quickref.asp), [C.L. Moffatt](https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins)

<br>

_댓글 환영합니다!_
