# 📈 Forecasting Sticker Sales

![Kaggle](https://img.shields.io/badge/Kaggle-Competition-blue?style=flat&logo=kaggle)

## 📌 개요
- **대회 이름**: [Forecasting Sticker Sales](https://www.kaggle.com/competitions/playground-series-s5e1/overview)  
- **목표**: 다양한 국가들의 가상 매장에서 Kaggle 브랜드 스티커 판매량을 예측  
- **진행 기간**: 2025.01.01 ~ 2025.01.31  
- **사용 기술**:  
  ➤ RandomForest 🌳🦌  <br>
  ➤ XGBoost 🔥  <br>
  ➤ Time Series Forecasting 📈  <br>
  ➤ LightGBM 🌟  <br>
  ➤ Optuna 🍣  <br>
  ➤ Feature Engineering 🔧  

---

## 📊 대회 정보
<details>
  <summary><b>📌 Overview (대회 개요)</b></summary>

  - **목적**: 머신러닝을 활용하여 시계열 데이터 기반으로 스티커 판매량 예측  
  - **평가 방식**: `MAPE (Mean Absolute Percentage Error)`
  - **제출 형식**: 날짜별로 각 제품의 예상 판매량 제출  

  🔗 **[대회 페이지 바로가기](https://www.kaggle.com/competitions/playground-series-s5e1/overview)**
</details>

<details>
  <summary><b>📂 Data (데이터 정보)</b></summary>

  - **데이터 개요**  
  이 데이터 세트는 가상의 Kaggle 브랜드 스티커 판매 기록을 포함하고 있으며, 주말 및 휴일 효과, 계절성 등 실제 데이터에서 볼 수 있는 다양한 패턴을 반영합니다.  

  - **파일 설명**  
    - `train.csv`: 날짜-국가-매장-품목 조합에 대한 판매 데이터를 포함하는 학습 데이터셋  
    - `test.csv`: 예측해야 하는 테스트 데이터셋 (각 날짜-국가-매장-아이템 조합에 대한 판매량 예측)  
    - `sample_submission.csv`: 올바른 제출 형식의 샘플 파일
  - **주요 컬럼**:
    - `date`: 날짜  
    - `country`: 국가  
    - `store`: 매장 ID  
    - `product`: 제품 ID  
    - `sales`: 판매량 (타겟 변수)  

  🔗 **[데이터 페이지 바로가기](https://www.kaggle.com/competitions/playground-series-s5e1/data)**
</details>

<details>
  <summary><b>📜 Rules (대회 규칙)</b></summary>

  - **허용된 기술**: 어떤 모델이든 사용 가능 (딥러닝, 머신러닝 등)  
  - **외부 데이터**: 사용 금지  
  - **제출 제한**: 하루 최대 5회 제출 가능  
  - **최종 평가 기준**: 공개 리더보드(50%) + 비공개 리더보드(50%)  

  🔗 **[규칙 페이지 바로가기](https://www.kaggle.com/competitions/playground-series-s5e1/rules)**
</details>

---

## 📊 데이터 및 전처리
<details>
  <summary><b>📂 데이터 설명 (클릭해서 열기)</b></summary>

  - **주말 효과**: 주중보다 주말에 판매량이 증가하는 패턴이 존재  
  - **휴일 효과**: 특정 국가별 공휴일에는 판매량이 급증 또는 급감  
  - **계절성 패턴**: 연말연시, 명절 등 특정 기간에 판매량 증가  
  - **요일별 판매 경향**: 주초(월요일)보다 주말(금~일) 판매량이 높음  
  - **매장별 특성 차이**: 동일한 국가에서도 매장별로 판매량 차이가 있음  
  - **제품별 인기도 차이**: 특정 제품이 국가 또는 매장별로 더 많이 판매됨
  - **결측치 처리**: 모든 결측치는 `0`으로 대체  

</details>

---

## 🔥 모델링 과정
<details>
  <summary><b>🛠 모델 개발 및 학습 과정 (클릭해서 열기)</b></summary>

  - **사용한 모델**: RandomForest, XGBoost, LightGBM 
  - **하이퍼파라미터 튜닝**:
    - RandomForest: `n_estimators=100, random_state=42`
    - Optuna 
    - LightGBM: `learning_rate=0.05, max_depth=7`  
  - **교차 검증 전략**: TimeSeriesSplit 적용  

</details>

---

## 📈 결과 및 성능 비교 (🏆 최종 결과 발표)
<details>
  <summary><b>📢 최종 결과 (클릭해서 확인)</b></summary>

  🎉 **최종 수상자 발표!** 🎉  

  | Rank  | Team Name       | Model                                      | Score   |
  |-------|---------------|------------------------------------------|---------|
  | 🏆 1st  | **SmileKim**  | `RandomForestRegressor(n_estimators=100, random_state=42)` | **0.18079** |
  | 🥈 2nd  | **y10.05b**  | `XGBRegressor + Optuna (Hyperparameter Tuning)` | **0.38940** |
  | 🥉 3rd  | **K2yoon(omit)** | `🥹 LightGBM + Feature 🥹`                    | **0.85486** |

</details>


---

## 🚀 인사이트
<details>
  <summary><b>📌 분석 인사이트 (클릭해서 보기)</b></summary>

  - **주요 인사이트**:  
    - 요일별 판매량 차이가 큼 (주말 판매량 증가)  
    - 국가별로 시계열 패턴이 다름  

</details>

