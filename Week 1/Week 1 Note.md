## 워밍업 겸 간단 복습 & 연습문제 풀기

1. 집계하기 GROUP BY

- 사용데이터 : solvesql Waiters Tips
- 문제 : 요일별 매출액 집계하여 소수점 둘째자리까지 출력하시오
- 정답 :
```
SELECT day
       , ROUND(SUM(total_bill),2) AS sales
FROM tips
GROUP BY day
```

2. 테이블 피봇
- 사용데이터 : solvesql Waiters Tips
- 문제 : 아래 형식에 맞춰 요일별, 시간대별 매출액을 집계하시오.  

|day |lunch|dinner|
|:--:|:---:|:----:|
|Sun |     |      |
|Sat |     |      | 
|Thur|     |      | 
|Fri |     |      | 

- 정답 :
```
SELECT day
       , CASE WHEN time = 'Lunch' THEN ROUND(SUM(total_bill),2) ELSE 0 END AS Lunch 
       , CASE WHEN time = 'Dinner' THEN ROUND(SUM(total_bill),2) ELSE 0 END AS Dinner 
FROM tips
GROUP BY day
```

3. 첫 주문과 마지막 주문
- 사용데이터 : solvesql Brazilian E-Commerce Public Dataset by Olist
- 문제 : 첫 주문 일자와 마지막 주문 일자를 나타내는 쿼리를 작성하시오
- 정답 :
```
SELECT DATE(MIN(order_purchase_timestamp)) AS first_order_date 
       , DATE(MAX(order_purchase_timestamp)) AS last_order_date 
FROM olist_orders_dataset
```

4. 배송 예정일 예측 성공과 실패
- 사용데이터 : solvesql Brazilian E-Commerce Public Dataset by Olist
- 문제 : 2017년 1월 한달동안 구매일자별로 배송일자 안에 도착한 주문과 배송일자 안에 도착하지 못한 주문을 구하는 쿼리를 작성하시오 (데이터가 없는 경우 제외합니다)
```
SELECT DATE(order_purchase_timestamp) as purchase_date
       , COUNT(case when order_delivered_customer_date <= order_estimated_delivery_date 
                    then order_id end)                                                   as 'success'
       , COUNT(case when order_delivered_customer_date > order_estimated_delivery_date 
                    then order_id end)                                                   as 'fail'
FROM olist_orders_dataset
WHERE order_purchase_timestamp BETWEEN '2017-01-01 00:00:00' AND '2017-01-31 23:59:59' 
      AND order_delivered_customer_date IS NOT NULL
      AND order_estimated_delivery_date IS NOT NULL
GROUP BY purchase_date
ORDER by purchase_date
```

5. 단일행 서브쿼리
- 사용데이터 : solvesql Waiters Tips
- 문제 : 평균 영수 금액보다 더 많이 지불한 경우를 출력하시오
- 정답 :
```
SELECT total_bill
FROM tips
WHERE total_bill >
                  (
                    SELECT AVG(total_bill)
                    FROM tips
                  )
```

6. 다중행 서브쿼리
- 사용데이터 : solvesql Waiters Tips
- 문제 : 요일별 판매금액이 1500 이상인 날의 결제내역을 출력하시오
- 정답 :
```
SELECT *
FROM tips
WHERE day IN
            (
              SELECT day
              FROM tips
              GROUP BY day
              having sum(total_bill) >= 1500
            )
```

7. FROM 절 서브쿼리1)
- 사용데이터 : solvesql Waiters Tips
- 문제 : 요일별 총 매출액 평균을 구하시오
- 정답 :
```
SELECT AVG(total_bill)
FROM
    (
      SELECT day, SUM(total_bill) as total_bill
      FROM tips
      GROUP BY day
    )
```

8. FROM 절 서브쿼리2)
- 사용데이터 : solvesql Waiters Tips
- 문제 : 요일별 매출액에서 영수금액이 차지하는 비율을 소수 둘째자리까지 구하시오.
- 정답 :
```
SELECT tips.day
       , total_bill
       , ROUND(total_bill/day_total_bill*100, 2) AS pct
FROM tips
LEFT JOIN
          (
            SELECT day, SUM(total_bill) as day_total_bill
            FROM tips
            GROUP BY day
          )  A
ON tips.day = A.day
ORDER BY total_bill DESC
```

9. SELEC절 서브쿼리
- 사용데이터 : solvesql Waiters Tips
- 문제 : 영수금액이 이 레스토랑의 전체 매출액에서 차지하는 비율을 소수 둘째자리까지 구하시오
- 정답 :
```
SELECT tips.day
       , total_bill
       , ROUND((total_bill / (SELECT SUM(total_bill) FROM tips)*100),2) AS pct
FROM tips
ORDER BY total_bill DESC
```
