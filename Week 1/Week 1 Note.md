## 워밍업 겸 간단 복습 & 연습문제 풀기

1. 집계하기 GROUP BY

- 사용데이터 : solvesql Waiters Tips
- 문제 : 요일별 매출액 집계하여 소수점 둘째자리까지 출력하시오
```
SELECT day
       , ROUND(SUM(total_bill),2) AS sales
FROM tips
GROUP BY day
```

2. 테이블 피봇
- 사용데이터 : solvesql Waiters Tips
- 문제 : 아래 형식에 맞춰 요일별, 시간대별 매출액을 집계하시오.  
|day|lunch|dinner|
|---|-----|------|
|Sun|     |      |
|Sat|     |      | 
|Thur|     |      | 
|Fri|     |      | 
