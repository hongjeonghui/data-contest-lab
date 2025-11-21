# EDA Summary Report

## 1. 데이터 구조 개요
- 데이터는 날짜(Date)와 품목(Item)별 월간 수입량(value)으로 구성된 시계열 형태.
- 기간: 2022-01 ~ 2025-07 (약 40개월)
- 각 Item은 난수형 코드로 제공되며 도메인 정보가 없음.
- 대부분의 Item은 월별로 요동하며 뚜렷한 계절성은 보이지 않음.

## 2. 상관관계 분석 결과
### 2.1 강한 상관 관계 그룹 존재
- 상관계수 0.99~1.00 수준의 극단적인 공행성 그룹 다수 발견.
- 일부 Item은 거의 동일한 파형을 공유함.
- PLMZALFA, RUVXNNVA 등이 중심 노드처럼 여러 품목과 연관됨.

### 2.2 구조적 특징
- 특정 Item끼리는 사실상 복제 수준으로 동일한 움직임.
- 일부 Item은 독립적으로 움직이며 상관이 거의 없음.

## 3. 시차(Cross-correlation) 분석 결과
### 3.1 선행–후행 구조 존재
- 상관 상위 쌍을 시차 분석한 결과, 대부분 lag = -6에서 최대 상관.
- lag = -6 → 두 번째 Item(item_b)이 첫 번째 Item(item_a)보다 6개월 먼저 움직임.

### 3.2 대표적인 선행–후행 관계 (선행 → 후행)
- PLMZALFA → DJBLNPNC  
- PLMZALFA → FTSVTTSR  
- ZKENOUDA → PLMZALFA  
- XIEJNEE → TANNMIMB  
- TANNMIMB → BLANHGYY  
- VUAFAIYJ → PLMZALFA  
- RUVXNNVA → LLHREMKS  
- RUVXNNVA → KJNSOAHR  

### 3.3 시각화 검증
- lag 6개월 적용 시 두 시계열이 거의 완전히 겹침.
- 우연이 아니라 구조적인 선행–후행 패턴임을 확인.

## 4. 데이터 전반 구조 요약
- 데이터는 여러 Item이 서로 얽힌 다중 시계열 구조.
- 세 가지 유형으로 나눌 수 있음:
  1) 동일 파형 그룹  
  2) 선행–후행 관계 그룹  
  3) 독립적/잡음형 Item  

## 5. 모델링 방향 추천
### 5.1 Feature Engineering
- lag feature 생성 필수 (특히 lag6)
- 상관 높은 Item은 제거 또는 PCA로 압축
- 선행 Item의 lag feature를 후행 Item 예측에 활용

### 5.2 모델 제안
- LightGBM / XGBoost 추천 (가장 안정적)
- Lasso/ElasticNet 기반의 회귀 모델도 적합
- LSTM/GRU는 데이터 길이가 짧아 주의 필요

## 6. 결론
- 데이터는 단순 시계열이 아니라 명확한 그룹 구조와 선행 지표를 가진 형태.
- EDA를 통해 중요한 관계(공행성·시차 구조)를 충분히 파악함.
- 이후 모델링에서는 lag 구조를 반영한 feature engineering이 핵심이 될 것.
