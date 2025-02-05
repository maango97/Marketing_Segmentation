# 🛍이커머스 고객 세분화 분석 

- 주제 : **이커머스 고객 세분화 분석 - 군집 분석과 RFMV를 이용한 초세분화 마케팅 전략**
- 기간 : 2024.12 - 2025.01 (5인)
- [데이터 출처(DACON)](https://dacon.io/competitions/official/236222/data)
- [최종 PPT]()
- [태블로 대시보드](https://public.tableau.com/app/profile/.30606921/viz/_17373700099870/34?publish=yes)


## 📋분석 개요


- **문제 정의**

  - 중국발 C커머스의 등장으로 인한 이커머스 시장 경쟁 심화와 경기 불황으로 소비 심리가 위축된 상황
  - 고객 세그멘테이션 기법을 통해 고객 가치와 구매 패턴에 대해 분석하여 고객 충성도를 높이고 매출 증대를 도모하는 것이 목표임
    
- **EDA 및 파생변수 생성**

  - 데이터 탐색을 위해 코호트 분석, 파레토 분석, 구매 패턴 분석, 카테고리 분석 등을 진행
  - 클러스터링을 위해 파생 변수 8개를 생성
 
- **1차 세분화 - 군집 분석**
  
  - Min-Max 정규화, PCA 시행
  - 파생변수들의 모든 조합을 각 모델에 적용하여 실루엣 점수가 가장 높게 나온 변수의 조합을 채택
  - 군집화 모델은 Birch, K-Medoids, K-Means를 비교 -> 전체 평균 실루엣 점수와 클러스터별 실루엣 점수를 모두 고려하여 **K-Means** 채택
  - 고객을 4개의 클러스터로 분류하여 각각의 특성과 전략을 수립
    
- **2차 세분화 - RFMV 분석**

  - RFMV란? 기존의 RFM에 V(Variety, 카테고리 다양성)을 추가 채택, 고객이 플랫폼을 얼마나 폭넓게 활용하는지와 충성도에 대해 확인 가능
  - 점수 기준? RFMV 각 컬럼별로 데이터 값을 기준으로 5분위수를 적용, 1~5점을 부여. 3점 이상이면 U(Up), 3점 미만이면 D(Down)로 분류
 
- **고민의 흔적들**

  - 비지도 학습이다 보니 세분화 기준을 정하는 데에 어려움을 겪음
    
    - 세분화 기준을 '양질의 군집화'로 정하고 수익 증대를 위한 마케팅 관점에서 파생변수를 생성, 기존 RFM 변수를 이용했을 때보다 높은 실루엣 계수를 가진 군집화에 성공
      
  - 2차 세분화 기준이자 이커머스의 성장 가능성을 평가하는 지표 선정
    
    - **고객의 해당 플랫폼 의존도**가 미래 성장 가능성에 크게 기여한다고 판단, 기존 RFM 기법에 V(카테고리 다양성)를 추가


## ⚙환경

- Anaconda - Jupyter Notebook
