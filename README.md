# **김민지 포트폴리오**
안녕하세요. 궁금했던 사안에 관해 질문하고, 데이터를 통해 답한 기록입니다.

- **활용툴**: Microsoft SQL Server, Tableau Public, Excel, ChatGPT
- **참고도서**: <나의 첫 SQL 수업>, <태블로 굿모닝 굿애프터눈>, <SQL로 맛보는 데이터 전처리 분석>
- **태블로**:  [프로필](https://public.tableau.com/app/profile/mzkim/vizzes)<br><br/>

<br><br>

## **1. 데이터 분석**
#### **# 피자 할인 쿠폰을 어떤 방식으로 발행할 수 있을까? ([코드보기](https://github.com/mzkim-ny/portfolio/blob/main/%ED%94%BC%EC%9E%90%20%EB%8D%B0%EC%9D%B4%ED%84%B0))** 
- **목적**: 1인 피자 시장이 커짐에 따라, 할인 쿠폰 발행 시 참고하기 위함입니다.
- **데이터**: Pizza Sales (데이터원본)
- **추출지표**:<br>
1\) 총 주문 금액, 총 주문 건수, ID당 평균 매출액, ID당 평균 주문 건 <br>
2\) 사이즈별 매출비율(ID당 주문이 한 건일때/아닐 때)<br>
3\) 사이즈/시간/요일별 주문 건수
4\) 사이즈/시간/요일별 가장 많이 구매한 메뉴 5가지<br>
- **시각화**: 지표를 산출하고, '사이즈별 매출비율'을 진행 그래프로 표현하였으며, '사이즈/시간/요일별 주문 건수'는 하이라이트 테이블로, '가장 많이 구매한 메뉴 5가지'는 트리맵 차트로 시각화하였습니다. ([태블로](https://public.tableau.com/shared/4FKB8ZMXH?:display_count=n&:origin=viz_share_link))
- **해석**: ID당 주문이 한 건이어도, S사이즈를 먼저 선택하지 않는 것으로 보입니다. 주문비율과 매출비율 모두 L사이즈가 가장 높고, 다음으로는 M사이즈, S사이즈입니다. 사이즈별로 선호하는 메뉴가 다르며, 주문 시간간이 달라져도 사이즈별 선호하는 메뉴는 그리 변하지 않는 점을 발견하였습니다.
- **제언**: 1인 피자 시장에서 S사이즈 피자 수요가 늘어나고 있다면, S사이즈를 가장 많이 주문하는 목요일 12시에, 인기 메뉴에 한정하여 할인 쿠폰을 발행하는 이벤트를 제안합니다.



#### **# 슈퍼스토어의 다음 이벤트는 어떻게 진행하면 좋을까? ([코드보기](https://github.com/mzkim-ny/portfolio/blob/main/%EC%8A%88%ED%8D%BC%EC%8A%A4%ED%86%A0%EC%96%B4))** 
- **목적**: 이벤트를 진행한다면, 어떤 상품을 어떤 가격에 판매하면 좋을지 알아보기 위함입니다.
- **데이터**: Superstore Sales (from Tableau)
- **추출지표**:<br>
1\) 매출액(일자별, 월별, 연도별)<br>
2\) 구매자 수, 구매 건수(일자별, 월별, 연도별)<br>
3\) 인당 매출액(AMV, Average Member Value) (연도별)<br>
4\) 건당 구매 금액(ATV, Average Transaction Value) (연도별)<br>
5\) 매출액(국가별, 도시별, 지역별)<br>
6\) 매출 TOP 5 도시(West)<br>
7\) 매출 TOP 10 품목(West, Los Angeles, 2017)<br>
8\) 재구매율(지역별, 연도별)<br>
- **시각화**: 고객이 재구매를 하기까지 기간이 얼마나 소요되었는지, 하이라이트 테이블로 표현하였습니다. ([코호트분석](https://public.tableau.com/views/240922_/2?:language=ko-KR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)) 
- **해석**: 매출액, 구매자 수, 구매 건수, 인당 매출액은 연도별로 증가하였으나, 건당 구매 금액은 하락하였습니다. 가장 매출액이 높은 서부 지역에서, 도시별, 품목별 판매 순위를 추가로 추출해 보았더니, 재구매율은 지역별로는 차이를 보이지 않지만, 연도별로는 상승한다는 점을 확인하였습니다.
- **제언**: 고객이 점점 넓은 간격으로 보다 저렴한 상품을 반복 구매한다고 보여집니다. 이벤트를 진행한다면, 인기 차트 중에 상대적으로 가격이 저렴한 상품을 선정하는 것을 제안합니다.


## **2. 대시보드로 현황 파악**
#### **# 코로나19 이후 영화관을 찾는 관객은 얼마나 될까? ([코드보기](https://github.com/mzkim-ny/portfolio/blob/main/%EC%BD%94%EB%A1%9C%EB%82%9819%EC%9D%B4%ED%9B%84%20%EC%98%81%ED%99%94%EA%B4%80%20%EB%A7%A4%EC%B6%9C%EC%95%A1%20%EB%B0%8F%20%EA%B4%80%EA%B0%9D%EC%88%98%20%EC%B6%94%EC%9D%B4))  - [태블로](https://public.tableau.com/views/19_17186243860350/2_1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)** 
- **데이터**: 영화관 입장권 통합전산망(2024.06)
- **목적**: 코로나19 이후 영화산업이 얼마나 회복되었는지 확인하기 위함입니다.
- **시각화**: 국가별 추이(전체영화, 한국영화, 외국영화)가 어떠한 변화를 보이는지, 년도, 매출액, 관객 수, 영화 수를 조건으로 두고, 누적 그래프와 숫자로 표현하였습니다.
- **해석**: 2019년과 2023년을 비교했을 때, 매출액보다 관객 수 회복 비율이 낮습니다. 매출액이 상승한 이유가 영화 티켓값 인상 때문인지 혹은 특정 굿즈 구매가 증가하였는지 추가 분석이 필요합니다.


#### **# 정약용도서관에서는 어떤 책이 많이 대출되었을까? ([코드보기](https://github.com/mzkim-ny/portfolio/blob/main/%EC%A0%95%EC%95%BD%EC%9A%A9%EB%8F%84%EC%84%9C%EA%B4%80%EC%97%90%EC%84%9C%EB%8A%94%20%EC%96%B4%EB%96%A4%20%EC%B1%85%EC%9D%B4%20%EB%A7%8E%EC%9D%B4%20%EB%8C%80%EC%B6%9C%EB%90%98%EC%97%88%EC%9D%84%EA%B9%8C%3F))  - [태블로](https://public.tableau.com/views/_17196652852140/1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)**
- **데이터**: 남양주시 정약용도서관 장서 대출목록(2024.05)
- **목적**: 정약용도서관 이용자의 독서 취향을 파악하기 위함입니다.
- **시각화**: 도서 대출 비율에 따라 십진분류 카테고리를 원그래프로 시각화하였습니다. 각 원을 클릭하면, 대출목록 TOP 10, 대출 횟수, 총 대출 건수, 총 보유 권수가 표시됩니다.
- **해석**: 가장 많이 대출하는 문학과 사회과학을, 접근성이 좋은 자료실 입구에 배치한 점이 적절해보입니다.
- **제언**: 이벤트 서가 코너에 새로운 책을 비치할 때, 보유 권수는 많지만 대출 건수가 저조한 카테고리의 책을 고려해볼 수 있겠습니다.


#### **# 남양주에는 반려견이 얼마나 살까? (Excel)   - [태블로 1](https://public.tableau.com/app/profile/mzkim/viz/3_17178536456650/1)&nbsp;- [태블로 2](https://public.tableau.com/shared/35Z4SXZ2H?:display_count=n&:origin=viz_share_link)**
- **데이터**: 남양주시 반려동물 등록현황(개)(2024.02), 남양주시 인구통계(2024.05)
- **목적**: 남양주 시민의 반려동물(개) 양육 현황을 파악하기 위함입니다.
- **해석**: 남양주시 내에서 반려견 등록이 가장 많은 읍면동은 화도읍(10,306마리), 다산1동(6,390마리), 별내동(5,893마리) 순으로 나타나며, 이는 주민등록 인구가 가장 많은 세 읍면동과 유사합니다.
- **제언**: 구리시는 반려동물 놀이터를 설치하여 만족도를 실험해보고 있습니다. 남양주시도 시범 운영을 해본다면, 면적 수 대비 반려견 등록 수가 가장 많은, 다산 1동에서 먼저 시작해보는 걸 추천합니다. 반려동물 놀이터 하나당 이용률을 높일 수 있고 여러 의견을 청취해볼 수 있습니다.


#### **# 지금 탕후루매장 인기는 어떠할까? ([코드보기](https://github.com/mzkim-ny/portfolio/blob/main/%ED%83%95%ED%9B%84%EB%A3%A8%EB%A7%A4%EC%9E%A5%20%EA%B0%9C%EC%97%85%20%EB%B0%8F%20%ED%8F%90%EC%97%85%20%EC%88%98))  - [태블로](https://public.tableau.com/views/2024_06_1/1_1?:language=ko-KR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**
- **데이터**: 지방행정 인허가 데이터개방(2024.06)
- **목적**: 탕후루 매장이 폐업하고 있다는 뉴스가 보도되었습니다. 얼마나 가파르게 진행되고 있는지 확인하기 위함입니다.
- **해석**: 2024년 1월부터 6월까지 폐업한 탕후루 매장은 총 163곳으로, 지난해 폐업한 매장(72곳)보다 많습니다. 탕후루 개업 매장 수는 2023년 3분기에 정점을 찍고, 점점 감소하고 있으며, 최근 감소 추세가 가팔라지고 있습니다.
- **제언**: 탕후루매장의 개점 및 폐점 속도가 유독 빨랐던 것인지, 다른 업종 데이터와 비교해보면 차이를 확인할 수 있겠습니다.


## **3. SQL로 지표 추출**
#### #. 전자 제품 데이터를 이용한 리포트 작성 ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%A0%84%EC%9E%90%20%EC%A0%9C%ED%92%88%20%ED%8C%90%EB%A7%A4%20%EB%8D%B0%EC%9D%B4%ED%84%B0)) (←클릭하시면 링크로 연결됩니다.)
- **데이터**: Customer purchase behavior - Electronic Sales Data (데이터원본)
- **목적**: SQL로 목적에 맞게 여러 지표를 추출해보기 위합니다.
- **추출지표**:<br>
1\) 상품별 구매자 수 및 매출액<br>
2\) 가장 많이 판매된 2개 카테고리 조회 (판매 상품 수 기준)<br>
3\) 2)번 구매자가 구매한 다른 카테고리 <br>
4\) 결제수단별 재구매율 계산 (2023년)<br>
5\) 코호트 분석<br>
6\) 고객 세그먼트 (RFM Score, K Means Algorithm) <br>
7\) 일자별 첫 구매자 수<br>
8\) 상품별 첫 구매 고객 수<br>
9\) 첫 구매 후 이탈하는 고객의 비중<br>
10\) 판매 수량이 20% 이상 증가한 상품 리스트 (YTD)<br>
11\) 주차별 매출액<br>
12\) 신규/기존 고객의 2024년 월별 매출액 <br>
13\) 기존 고객의 2024년 월 누적 리텐션 - [태블로](https://public.tableau.com/app/profile/mzkim/viz/2024_17288177678440/1)<br>
14\) 2023년 구매자의 LTV (Life Time Value)<br>
