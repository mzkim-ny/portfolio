# **김민지 포트폴리오**
안녕하세요. 궁금했던 사안에 관해 질문하고, 데이터를 통해 답한 기록입니다.

- **활용툴**: Excel, MSSQL, Tableau Public, ChatGPT
- **참고도서**: <나의 첫 SQL 수업>, <태블로 굿모닝 굿애프터눈>, <SQL로 맛보는 데이터 전처리 분석>
- **태블로**:  [프로필](https://public.tableau.com/app/profile/mzkim/vizzes)<br><br/>

## **1. 지표 분석**
#### **# S사이즈 피자 쿠폰을 발행한다면? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%ED%94%BC%EC%9E%90%20%EB%8D%B0%EC%9D%B4%ED%84%B0))** (←클릭하시면 링크로 연결됩니다.)
- **데이터**: Pizza Sales (from Kaggle)
- **목적**: 1인 피자 시장이 커짐에 따라, S사이즈 피자 판매 현황을 파악하고, 인사이트를 도출하기 위함입니다.
- **코드**: 전체 주문 건수, 전체 구매자 수(중복 포함), 상품별 주문 건수, 시간별 주문 건수, 주문 건당 평균 구매자 수(중복 포함), 사이즈별 주문 건수, 시간대별 S사이즈 주문 건수, 피크타임별 구매가 가장 많은 S사이즈 상품 5개, 피크타임별 구매가 가장 많은 S사이즈 옵션 5개, 사이즈별 구매가 가장 많은 상품 5개를 추출하였습니다.
- **제언**: S사이즈는 12시와 18시에 구매가 가장 많지만, 메뉴 및 옵션에서는 차이를 거의 보이지 않습니다. 메뉴는 두 시간대 모두 빅미트, 하와이안, 클래식 DLX, 페퍼로니, 시칠리안 피자가 인기 있으며, 옵션은 클래식, 슈프림, 베지, 치킨 순으로 판매되었습니다. 오히려 사이즈별로 유의미한 차이는 메뉴에서 보입니다. L사이즈는 타이 치킨, 파이브 치즈, 포 치즈, 스파이시 이탈, 사우스웨스트 치킨이 판매량이 많습니다. S사이즈 피자 판매를 늘리기 위해서는 특정 메뉴에 쿠폰을 발행하는 전략이 유효할 것 같습니다.
- **한계**: 구매자별 고유값이 없기 때문에, 재구매에 관한 지표는 산출하기 어렵습니다.

## **2. 대시보드**
#### **# 코로나19 이후 영화관을 찾는 관객은 얼마나 될까? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%BD%94%EB%A1%9C%EB%82%9819%EC%9D%B4%ED%9B%84%20%EC%98%81%ED%99%94%EA%B4%80%20%EB%A7%A4%EC%B6%9C%EC%95%A1%20%EB%B0%8F%20%EA%B4%80%EA%B0%9D%EC%88%98%20%EC%B6%94%EC%9D%B4))  - [태블로](https://public.tableau.com/views/19_17186243860350/2_1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)** (←클릭하시면 링크로 연결됩니다.)
- **데이터**: 영화관 입장권 통합전산망(2024.06)
- **목적**: 코로나19 이후 영화산업이 얼마나 회복되었는지 확인하기 위함입니다.
- **코드**: 국가별로 나눠진 세 개의 테이블을 하나의 테이블로 합쳐 필요한 칼럼을 추출하였으며, 칼럼에 값이 없으면 문자를 입력하였습니다.
- **대시보드**: 국가별 추이(전체영화, 한국영화, 외국영화)가 어떠한 변화를 보이는지, 년도, 매출액, 관객 수, 영화 수를 조건으로 두고, 누적 그래프와 숫자로 표현하였습니다.
- **제언**: 2019년과 2023년을 비교했을 때, 매출액보다 관객 수 회복 비율이 낮습니다. 매출액이 상승한 이유가 영화 티켓값 인상 때문인지 혹은 특정 굿즈 구매 증가 때문인지 분석이 필요해 보입니다.
- **한계**: 공공데이터로는 개인식별정보에 접근할 수 없는 어려움이 있습니다.


#### **# 정약용도서관에서는 어떤 책이 많이 대출되었을까? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%A0%95%EC%95%BD%EC%9A%A9%EB%8F%84%EC%84%9C%EA%B4%80%EC%97%90%EC%84%9C%EB%8A%94%20%EC%96%B4%EB%96%A4%20%EC%B1%85%EC%9D%B4%20%EB%A7%8E%EC%9D%B4%20%EB%8C%80%EC%B6%9C%EB%90%98%EC%97%88%EC%9D%84%EA%B9%8C%3F))  - [태블로](https://public.tableau.com/views/_17196652852140/1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)**
- **데이터**: 남양주시 정약용도서관 장서 대출목록(2024.05)
- **목적**: 정약용도서관 이용자의 독서 취향을 파악하기 위함입니다.
- **코드**: 십진분류 칼럼을 주제분류번호를 기반으로 업데이트 하였고, 임시테이블을 만들어 특정 칼럼을 추출하고, 함수를 사용하여 필요한 숫자를 산출하였습니다.
- **대시보드**: 도서 대출 비율에 따라 십진분류 카테고리를 원그래프로 시각화하였습니다. 각 원을 클릭하면, 대출목록 TOP 10, 대출 횟수, 총 대출 건수, 총 보유 권수가 표시됩니다.
- **제언**: 가장 많이 대출하는 문학 카테고리를 자료실 입구에 서가 배치한 것은, 총 대출 건수를 늘리는 선택이었다고 생각합니다. 이벤트 서가 코너에 책을 배치할 때, 보유 권수는 많지만 대출 건수가 저조한 카테고리의 책을 고려해볼 수 있겠습니다.


## **3. 데이터 시각화**
#### **# 남양주에는 반려견이 얼마나 살까? (Excel)   - [태블로1](https://public.tableau.com/app/profile/mzkim/viz/3_17178536456650/1)&nbsp;- [태블로2](https://public.tableau.com/shared/35Z4SXZ2H?:display_count=n&:origin=viz_share_link)**
- **데이터**: 남양주시 반려동물 등록현황(개)(2024.02), 남양주시 인구통계(2024.05)
- **목적**: 남양주 시민의 반려동물(개) 양육 현황을 파악하기 위함입니다.
- **해석**: 남양주시 내에서 반려견 등록이 가장 많은 읍면동은 화도읍(10,306마리), 다산1동(6,390마리), 별내동(5,893마리) 순으로 나타나며, 이는 주민등록 인구가 가장 많은 세 읍면동과 유사하다.
- **제언**: 구리시는 반려동물 놀이터를 설치하여 만족도를 실험해보고 있습니다. 남양주시도 시범 운영을 해본다면, 면적 수 대비 반려견 등록 수가 가장 많은, 다산 1동에서 먼저 시작해보는 걸 추천합니다. 반려동물 놀이터 하나당 이용률을 높일 수 있고 여러 의견을 청취해볼 수 있습니다.

#### **# 지금 탕후루매장 인기는 어떠할까? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%ED%83%95%ED%9B%84%EB%A3%A8%EB%A7%A4%EC%9E%A5%20%EA%B0%9C%EC%97%85%20%EB%B0%8F%20%ED%8F%90%EC%97%85%20%EC%88%98))  - [태블로](https://public.tableau.com/views/2024_06__17185326601780/1_1?:language=ko-KR&publish=yes&:sid=&:display_count=n&:origin=viz_share_link)**
- **데이터**: 지방행정 인허가 데이터개방(2024.06)
- **목적**: 대세 간식으로 유행했던 탕후루의 인기가 여전히 유효한지 확인하기 위함입니다.
- **해석**: 2024년 1월부터 6월까지 폐업한 탕후루 매장은 총 163곳으로, 지난해 폐업한 매장(72곳)보다 많다. 탕후루 개업 매장 수는 2023년 3분기에 정점을 찍고, 점점 감소하고 있으며, 최근 감소 추세가 가팔라지고 있다.
- **제언**: 탕후루매장의 개점 및 폐점 속도가 유독 빨랐던 것인지, 일정한 주기가 있는 것인지 다른 업종 데이터와 대조해 보면, 보다 면밀한 분석이 가능할 것입니다.
