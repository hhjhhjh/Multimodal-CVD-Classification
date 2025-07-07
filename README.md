# 안저영상과 임상정보를 활용한 멀티모달 멀티태스크 딥러닝 기반 심혈관 질환 분류
# Multimodal Multitask Deep Learning for CVD Classification Using Fundus Images and Clinical Data

이 레포지토리는 안저영상(Fundus Image)과 임상정보(Clinical Data)를 함께 활용하여  
심혈관 질환(CVD)을 예측하는 멀티모달 멀티태스크 딥러닝 모델을 구현한 프로젝트입니다.

> 📄 논문 제목: 안저영상과 임상정보를 활용한 멀티모달 멀티태스크 딥러닝 기반 심혈관 질환 분류 (Multimodal Multitask Deep Learning for CVD Classification Using Fundus Images and Clinical Data)  
> ✍ 저자: 황정현

---

## 🧠 프로젝트 개요

- **목표**: 안저영상과 임상정보를 함께 입력으로 사용하여 심혈관 질환 유무를 예측
- **모달리티**:
  - 좌/우측 안저 이미지
  - 나이, 성별 (임상 정보)
- **모델 방식**:
  - 멀티모달 딥러닝
  - 멀티태스크 학습 (분류 + 회귀)

---

## 🔨 모델 구조

- **이미지 인코더**: EfficientNetV2-S 기반 CNN
- **임상정보 인코더**: 2-layer MLP
- **통합 방식**: 중간 특징 벡터 결합 (concatenation)
- **손실 함수**: Focal Loss (분류), MSE Loss (회귀 선택 시)
- **프레임워크**: PyTorch

---

## 📁 데이터셋

- **데이터 출처**: [China-Fundus-CIMT 공개 데이터셋](https://springernature.figshare.com/articles/dataset/High-resolution_fundus_images_for_ophthalmomics_and_early_cardiovascular_disease_prediction_China_Fundus_Carotid_Intima-Media_Thickness_dataset/27907056)
- **전처리 과정**:
  - 이미지 리사이징, 이미지 증강 기법 (회전, 수평-수직 반전, 밝기 및 색조 변화 등)
  - 임상정보 전처리 (원핫인코딩, 정규화)
  - 환자 단위 Train/Validation/Test 분할
    - 총 환자: 2903명 (훈련; 2603명, 검증: 200명, 테스트: 100명)

---

## 🚀 모델 아키텍처 

