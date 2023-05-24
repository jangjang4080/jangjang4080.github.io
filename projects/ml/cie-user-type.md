---
layout: page
title: 머신러닝(Machine Learning) 기반의 사용자 타입 분석
---

### 기술 스택
Python, Jupyter Notebook  

### 실행 환경
Mac    

---

## 사용자 타입 분석
머신러닝 비지도학습의 대표적인 클러스터링을 이용하여 사용자 타입을 분석합니다.  

### 클러스터링
엘보우, 실루엣 기법 등을 통해 클러스터 개수를 3개로 정했습니다. 여러 알고리즘들을 비교해 차원 축소(dimention reduction)는 SpectralEmbedding 알고리즘, 클러스터링은 GaussianMixture 알고리즘을 이용했습니다.  

![image](/assets/images/ml/1.png)

### 클러스터별 피처 평균 비율 - 히트맵으로 시각화
오른쪽 바에서 보는 것처럼 색깔이 밝아질수록 값이 큰 것을 의미합니다. 칸 안의 값들은 다른 클러스터들에 대한 상대적인 비율입니다.  

![image](/assets/images/ml/2.png)

### 원형 차트로 시각화 - 클러스터별 피처 평균의 비율
![image](/assets/images/ml/3.png)

---

## 결과

### 레벨 4 사용자 그룹의 ROC
![image](/assets/images/ml/4.png)

### 레벨 7 사용자 그룹의 ROC
![image](/assets/images/ml/5.png)