# Store_Sales_Predict
상점 신용카드 매출 예측

2020 - 11 - 23



상점 신용카드 매출 예측

- 소상공인 가맹점 신용카드 빅데이터와 AI로 매출 예측 분석
- 2019년 2월 28일까지의 카드 거래 데이터를 이용하여 2019년 3월 1일 ~ 5월 31일까지의 상점별 3개월 총 매출 예측
- 제공된 데이터의 레코드 단위는 ‘거래’이며, 예측하고자 하는 레코드의 단위는 3개월 간의 상점 매출임


< funda_train.csv : 모델 학습용 데이터 >

store_id : 상점의 고유 id
card_id : 사용한 카드의 고유 아이디
card_company : 비식별화된 카드 회사
transcated_date : 거래 날짜
transacted_time : 거래 시간
installment_term : 할부 개월 수
region : 상점 지역
type_of_business : 상점 업종
amount : 거래액


< submission.csv >
store_id: 상점의 고유 id


< 기본 데이터 구조 설계 >
레코드가 수집된 시간 기준으로 3개월 이후의 총 매출을 예측하도록 구조를 설계해야 함
ex)
상점 ID: 1, 시점: 4, 특징: 시점 1 ~ 3까지의 상점 1의 특징, 라벨: 시점 5 ~ 7까지의 상점 1의 매출 합계
상점 ID: 1, 시점: 5, 특징: 시점 2 ~ 4까지의 상점 1의 특징, 라벨: 시점 6 ~ 8까지의 상점 1의 매출 합계
상점 ID: 1, 시점: 6, 특징: 시점 3 ~ 5까지의 상점 1의 특징, 라벨: 시점 7 ~ 9까지의 상점 1의 매출 합계
상점 ID: 2136, 시점: 38, 특징: 시점 35 ~ 37까지의 상점 1의 특징, 라벨: 시점 38 ~ 40까지의 상점 1의 매출 합계
상점 ID: 2136, 시점: 38, 특징: 시점 36 ~ 38까지의 상점 1의 특징, 라벨: 시점 39 ~ 41까지의 상점 1의 매출 합계

시점의 정의 = ((년-2016)*12 + 월)
