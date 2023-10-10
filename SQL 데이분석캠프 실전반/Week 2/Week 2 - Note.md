## AARRR

1) AARRR이란? : 이 용어는 미국의 스타트업 엑셀러레이터인 500 Startups의 설립자인 데이브 맥클루어(Dave McClure)가 개발한 분석 프레임워크입니다. 스타트업은 아이디어를 바탕으로 서비스(상품)를 만드는 데 능숙하지만, 서비스를 효과적으로 사람들에게 알리고 사용자를 꾸준히 확보하기 위한 개선방법에 대해서는 고민이 많습니다. AARRR은 시장 진입 단계에 맞는 특정 지표를 기준으로 우리 서비스의 상태를 가늠할 수 있는 효율적인 기준이 됩니다. 수많은 데이터 중 현 시점에서 가장 핵심적인 지표에 집중할 수 있게 함으로써, 분석할 리소스(인력이나 시간)가 충분하지 않은 스타트업에게 매력적인 프레임워크라고 할 수 있습니다.
  
2) AARRR 단계별 핵심 지표
- Acquisition : 어떻게 우리 서비스를 접하고 있는가
- Activation : 사용자가 처음 서비스를 이용할 때 긍정적인 경험을 제공하는가
- Retention : 이후의 서비스 재사용률은 어떻게 되는가
- Referral : 사용자가 자발적 바이럴, 공유를 일으키고 있는가
- Revenue : 최종 목적(매출)으로 연결되고 있는가
  
![image](https://github.com/ellieso/sqldatacamp/assets/83899219/e79148db-4e14-4722-a204-4e238bbbe8e2)

 a) Acquisition (유입)  
*관련 데이터 : DAU, MAU, 앱설치수, 실행수  
*해야할 질문 : 어디에서 유입이 가장 많이 되었는가?  

반가운 신규 고객이 들어왔습니다!  이에 우리는 어디에서, 얼마나 많은 고객이 들어왔는지 최우선으로 확인해봐야합니다.   
마케팅을 진행하고 있다면 다수의 광고 채널 및 콘텐츠를 통해 신규 방문자가 들어올 텐데, 여기서 유입 수를 가장 잘 분석하는 방법은 하나입니다. 일일 유입수만 단순하게 확인하는 것을 넘어 미디어 파트너별, 캠페인별, 날짜별 데이터를 쪼개어 보아야합니다.   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/4eb03b0d-1140-4eea-b4f6-ba072be7160d)

위와 같은 트렌드 차트로 매체 및 일자별 광고클릭수에 따른 인스톨 수가 얼마나 되는가를 종합적으로 분석해야하는 것이죠. 이렇게 각각의 광고 매체로 들어온 유저들의 활동력을 비교해보며 살려야할 광고, 죽여야할 광고를 파악해 광고 최적화 진행하는 것이 Acquisition 단계에서 할 수 있는 최우선의 방법입니다. 

b) Activation (활성화)  

*관련 데이터 : 회원가입, 상품 조회, 장바구니 담기, 쿠폰 조회수, 좋아요 등  
*해야할 질문 : 어디에서 유저들이 이탈하는가?  

고객들이 우리 서비스를 어떻게 active 하게 이용하는가?를 판단하는 단계입니다.  
이 단계에선 주로 퍼널 분석을 이용하는데, 아직 고객 경로 및 활성화 kpi를 정하지 못한 경우 무엇을 주요 지표로 삼아야할 지 고민될 수 있습니다. 이커머스 비즈니스를 예로 들 때 상품조회, 장바구니 담기, 쿠폰 조회수..등 구매까지 갈 수 있는 이벤트들이 무궁무진하게 많지요. 따라서 그 우선순위를 쉽게 판별하기 위해, ‘유저플로우’라는 분석 기능을 활용하는 것이 좋습니다.   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/cba0b585-d864-4511-870f-4e39a360a8d8)

유저플로우는 유저가 앱 내에서 만들어낸 행동흐름을 이벤트 스텝별로 시각화 한 것입니다. 유저들이 구매활동까지 실제로 어떻게 활동하는 지, 무엇이 우선시 되는지 그 연관관계를 파악해보는 것이 중요합니다. 마케터의 단순한 예측에 따라 주요 지표를 선정하는 것보다, 실제 유저들의 이용 경로에 따른 데이터 결과를 살펴보고 결정하는 게 더 힘있는 결과를 내게되는 것이죠.   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/b1afcbf3-0b86-441e-a43a-f3c14fe8c14a)

유저플로우를 분석해보며 주요 지표를 정했다면, 이제 그것을 기반으로 퍼널을 분석해보겠습니다.  
퍼널은 마케터가 직접 이벤트(주요지표) 들을 순차적으로 설정하여 그 단계별 전환률/이탈률을 한눈에 볼 수 있는 기능입니다. 따라서 활성화의 주요지표를 ‘상품조회’ 로 하고 앱 오픈 – 상품조회 – 구매까지의 과정을 퍼널로 설정해볼때, 서비스를 이용하는 유저 맞춤 개선이 이루어지지 않은 경우 구매로 가는 과정에서 전환률이 쑥 깎이는 현상이 발생합니다.   
따라서 퍼널을 분석할 때도 다양한 기준을 통해 데이터를 비교해보는 것이 필요합니다. 서비스 기능을 업데이트한 일자가 있다면 그 기간과 기존 기간의 데이터를 비교하거나, 미디어 파트너를 기준으로 유입 경로에 따라 퍼널이 다른 경향이 있는지, 어떤 것을 원인으로 수치가 급감하였는지 꼼꼼히 분석하여 인사이트를 찾는 것이 필요합니다.   

c) Retention (유지)  

*관련 데이터 : 지표별 전환 및 이탈 유저  
*해야할 질문 : 고객의 재방문률은 어떻게 올리는가?   

- 유저 데이터 쉽게 추출하기  
일정 기간 이상 재방문하지 않는 고객을 다시 데려오는 것이 관건인 단계입니다.   
여기서는 리텐션 수치를 분석하는 방법보다, 어떻게 하면 효과적으로 리텐션 값을 올릴 수 있는지 실전에 입각하여 한번 살펴보겠습니다. 리텐션 상승이 필요한 유저 데이터를 어떻게 추출하고, 어떻게 리타겟팅하는 것인지 간단하게 알아볼거에요.  

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/03247a66-0eb9-4b70-9520-a0542c4e72b9)

위 이미지는 한달 동안 앱을 실행한 유저를 기준으로 ① 자연유입된 유저 / ② A 광고를 보고 유입된 유저로 퍼널을 생성한 것입니다. 수치를 보아하니 organic 과 A매체의 유입량도 다르고, 전환률도 각기 다른 것이 보이네요.   
데이터를 비교하는 과정에서 A매체와 같이 최종 구매로 5%밖에 전환이 안되는 퍼널을 발견했다면 이탈한 95% 유저들에게 한 번 더 어필하는 시도가 필요합니다. 이때 유저들에게 어필하기 위해선 그 유저들을 모아봐야하는데, 여기서 핵심은 각 단계의 퍼널을 클릭하면 우측에 보이는 바와 같이 전환/이탈 유저에 대한 식별자 값을 직접 받아볼 수 있다는 것입니다.   
유저 데이터를 직접받아봄으로써 우리는 A매체로 유입된 유저들의 취향에 맞추어 비슷한 소재로 리타겟팅 할 수 있는 것이죠.   

- 리텐션을 올리는 방법은?  
앱 리타겟팅하면 바로 떠오르는 쉬운 방식이 무엇인가요? 타겟에 따라 간단한 소재만 기획된다는 측면에서 푸시 메시지가 가장 합리적일거 같습니다.   
다만 효과가 높으려면 타겟을 잘 선정해야하는 것이겠죠. 따라서 앞에서 설명한 퍼널에서 유저 데이터를 추출하는 방법을 따라 해보거나, 마케팅 액션 대시보드에서 특정 조건들을 조합해 직접 타겟을 만들어보면 됩니다.  

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/4bdff46a-6bac-4d2b-89cd-a0417c86ae59)

위와 같이 최근 방문일, 누적 방문수, 유입매체 등을 체크하여 재방문이 필요한 유저들에게 딱 맞는 푸시메시지를 보내볼 수 있습니다. 구매한 사람에게 재구매를 유도하기 위해 포인트 적립을 알리거나, 미구매한 사람에겐 일정 시간이 지난 후 해당 상품을 저렴하게 살 수 있는 쿠폰을 발행하는 법이 있겠네요.  

d) Revenue (수익)   

*관련 데이터 : LTV, 구매금액  
*해야할 질문 : 구매력 높은 유저의 특성은?  

서비스가 유지되기 위해 가장 무시할 수 없는 것이 무엇일까요?   
마케터가 일희일비할 수 밖에 없는..! 바로 매출입니다.   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/0cf40adc-994b-4d53-887b-06766d5d4786)

매출을 잘 보는 방법에는 단순히 기간에 따른 매출 통합 수치를 보는 것도 좋지만, 마케팅 최적화를 위해 미디어 파트너별 유저들의 구매력이 어떻게 되는지 리텐션도 구분하여 확인하는 것이 좋습니다. 구매력이 높은 유저들을 유입시키는 매체를 선정해 마케팅 효과를 더욱 높일 수 있을테니까요!   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/7f3b4bb0-cb4a-46cf-8c98-12ea48286950)

또한 전체유저를 구매력에 따라 1~5티어로 나눠 매출, 구매자 수, ARPPU를 확인할 수 있는 구매자 티어 대시보드를 활용해도 좋습니다. 구매력에 따른 구매자 수와 티어별 오디언스 데이터를 다운 받아 앞으로 혜택을 어떻게 구성해야할지, 어떤 서비스나 상품을 유치해야하는지 판단하며 좋은 근거 자료로써 활용할 수 있습니다.  

e) Referral (추천)

*관련 데이터 : 공유하기, 친구 초대 수, 리뷰작성 수  
*해야할 질문 : 상품과 서비스의 추천도는 어떻게 되는가?  

고객들이 다른 사람들에게 제품에 대한 칭찬을 하는 것을 앱 마케팅에서 가장 쉽게 확인하는 방법은 바로 리뷰쓰기 입니다.   
보통 Referral 단계의 예시로는 인스타그램에 유저가 직접 제품에 대한 포스팅하거나 해시태그하는 등의 경우가 많은데, 이 부분은 현실적으로 트래킹 하기 어렵고 신뢰할 수 있는 데이터가 모이지 못할 수 있기 때문에 앱에서 측정가능한 ‘리뷰작성’ 이벤트 성과로 판단하는 것이 좋습니다.   

![image](https://github.com/ellieso/sqldatacamp/assets/83899219/19faa382-8a6a-4b83-8f26-62d5e239ba48)

마지막은 가장 종합적으로 성과를 확인할 수 있는 데이터표를 확인하면 좋습니다.   
데이터 표의 광고 클릭 및 인스톨 – 회원가입 및 상품조회 – 주문수 – 수익 – 여기에 ‘리뷰작성’ 지표 하나만 추가하면 되겠습니다.   

### “Retention 없는 Acquisition은 마케팅 예산 낭비”

기존 사용자들이 우리 서비스를 잘 사용하고 있는지, 지속적으로 사용하는지 관찰하는 Retention 지표들은 다른 어떤 단계의 지표들보다 가장 먼저 분석되어야 합니다. 그래서 어떤 사람들은 AARRR을 RARRA로 불러요. 가장 먼저 달성되어야 하는 지표 순서대로 Retention → Activation → Referral → Revenue → Acquisition 이렇게요.

## Cohort analysis

1. 코호트 분석 (Cohort Analysis)이란?
특정 기간 동안 공통된 특성이나 경험을 갖는 사용자 집단을 의미합니다. 첫방문, 캠페인 유입 등 특정 조건에 해당되는 사용자들을 그룹화하고 시간 흐름에 따른 행동 패턴을 추적합니다.  

2. 코호트 분석이 중요한 이유
   - 고객 유지율(Retention Rate) 분석
     이커머스에서 고객 유입 못지않게 중요한 것은 바로 고객 유지율입니다. 한 번 방문했던 고객들이 단발성 방문에 그치지 않고 지속적으      로 사이트에 재방문하고 자연스럽게 구매로 연결되어야 하기 때문인데요. 코호트 분석은 고객의 이탈 시점을 분석하는 데 있어 탁월한       분석 지표입니다!
   - 특정 고객 집단의 인사이트 발견  
     코호트 분석에서는 방문 X 구매 X 유입 X 광고 등의 세그먼트 조건을 조합하여 특정 고객군을 선정하고 분석할 수 있습니다. 자유로운       조건을 조합할 수 있어 마케터가 얻을 수 있는 인사이트가 확장됩니다. 특정일의 구매자, 회원가입 고객, 캠페인 유입 고객, 재방문, 
     재구매 주기와 같은 마케팅 현황을 진단해보세요. 문제점을 파악하고 효과적인 개선 전략을 세워볼 수 있습니다.
     
3. 코호트 분석을 통해 얻을 수 있는 인사이트
- 고객 유지율
- 고객 이탈률
- PC 웹 / 모바일 웹 / 하이브리드 앱 사용자 유지율 
- 시간 경과에 따른 마케팅 캠페인 효과 분석
- 신규 회원가입자의 유지율
- 유입 출처에 따른 고객 가치

## 클래식 리텐션

​클래식 리텐션은 유저들이 처음 서비스를 이용한 때를 기준으로 몇 일이 지난 시점에 얼마나 많은 사람들이 접속했는지를 계산하는 지표입니다. 클래식 리텐션은 매일 날짜를 기준으로 측정되기 때문에 Day-N 리텐션이라고 불리기도 합니다.  
예를 들어 2022년 1월 22일에 처음 가입한 유저가 100명이 있다고 했을 때, 이들 중 7일이 지난 1월 29일에 60명이 접속을 했다면 Day 7 리텐션은 60%가 됩니다.  
![image](https://github.com/ellieso/sqldatacamp/assets/83899219/e82aaf55-146f-4df8-a259-2329ad575dcd)

- 사용데이터 : US E-commerce Records 2020
- 문제 : 데이터를 바탕으로 리텐션 분석을 하시오
- 정답 :
```
select first_order_month
       , count(DISTINCT customer_id) as month0
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 1 month) = order_month
                        THEN customer_id 
                        END) as month1
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 2 month) = order_month
                        THEN customer_id 
                        END) as month2
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 3 month) = order_month
                        THEN customer_id 
                        END) as month3
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 4 month) = order_month
                        THEN customer_id 
                        END) as month4
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 5 month) = order_month
                        THEN customer_id 
                        END) as month5                      
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 6 month) = order_month
                        THEN customer_id 
                        END) as month6
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 7 month) = order_month
                        THEN customer_id 
                        END) as month7
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 8 month) = order_month
                        THEN customer_id 
                        END) as month8
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 9 month) = order_month
                        THEN customer_id 
                        END) as month9
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 10 month) = order_month
                        THEN customer_id 
                        END) as month10
       , count(DISTINCT CASE WHEN DATE_ADD(first_order_month, INTERVAL 11 month) = order_month
                        THEN customer_id 
                        END) as month11

FROM (
        select r.customer_id
              , r.order_id
              , r.order_date
              , DATE_FORMAT(r.order_date, '%Y-%m-01') as order_month
              , c.first_order_date
              , DATE_FORMAT(c.first_order_date, '%Y-%m-01') as first_order_month
        from records r
        inner join customer_stats c
        on r.customer_id = c.customer_id
      ) a
group by first_order_month
```
