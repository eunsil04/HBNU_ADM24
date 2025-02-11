# 🏆 Kaggle 1등 Solution - Stacking Ensemble Model

이 프로젝트는 **Stacking Ensemble Model**을 활용하여 예측 성능을 향상시키는 방법을 설명합니다.  
해당 모델은 여러 개의 기본 모델(Level 0)을 훈련한 후, 이들의 출력을 메타 모델(Level 1)에 입력하여 최종 예측을 수행합니다.

## 🔥 **Stacking 구조**
<img width="1091" alt="Image" src="https://github.com/user-attachments/assets/2dac990e-39a3-486f-b9f8-e6b2d8915e26" />

1. **Level 0 Modeling**  
   - 기본 모델(Base Model)로 **XGBoost, LightGBM, Gradient Boosting**을 사용합니다.
   - K-Fold Cross Validation (CV=5)를 활용하여 모델을 훈련하고 예측 결과를 생성합니다.
   - 이 과정에서 생성된 예측 결과는 `Meta Train Dataset`으로 변환됩니다.

2. **Level 1 Modeling**  
   - Level 0 모델에서 생성된 예측값을 입력(feature)으로 사용합니다.
   - **Logistic Regression**을 메타 모델(Meta Learner)로 사용하여 최종 예측을 수행합니다.


## 📌 **설치 및 실행 방법**
### 1️⃣ **필요한 패키지 설치**
```bash
pip install numpy pandas scikit-learn xgboost lightgbm matplotlib
