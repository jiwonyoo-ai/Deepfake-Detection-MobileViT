# Deepfake Detection with MobileViT

> A deepfake image and video detection system based on MobileViT.

딥페이크 이미지 및 영상의 진위 여부를 분류하는 **딥페이크 탐지 시스템**입니다.

본 프로젝트에서는 영상에서 프레임을 추출하고 전처리한 뒤, **MobileViT 기반 이미지 분류 모델**을 활용하여 Real / Fake를 분류했습니다. 또한 다른 딥러닝 모델과의 비교를 통해 모델별 탐지 성능을 분석했습니다.

---

## Project Overview

### Motivation

생성형 AI 기술의 발전으로 실제 콘텐츠와 구분하기 어려운 딥페이크 이미지와 영상이 증가하고 있습니다.

본 프로젝트에서는 **CNN의 특징 추출과 Transformer의 전역 정보 처리 특성을 결합한 MobileViT**를 활용하여 딥페이크 탐지 가능성을 확인하고, 다른 딥러닝 모델과 성능을 비교했습니다.

---

## System Pipeline

```text
Image / Video
     ↓
Frame Extraction
     ↓
Image Preprocessing
     ↓
MobileViT
     ↓
Binary Classification
     ↓
Real / Fake
     ↓
Performance Evaluation
```

---

## Workflow

### 1. Data Preprocessing

이미지 및 영상 데이터를 모델 학습에 사용할 수 있도록 전처리했습니다.

영상 데이터는 프레임 단위의 이미지로 변환하여 이미지 classification 방식으로 처리했습니다.

```text
Video
  ↓
Frame Extraction
  ↓
Resize / Normalization
  ↓
Model Input
```

### 2. MobileViT-based Classification

MobileViT를 딥페이크 탐지를 위한 classification model로 활용했습니다.

CNN 기반의 local feature extraction과 Transformer 기반의 global representation을 결합한 구조를 통해 이미지의 시각적 특징을 학습하고 **Real / Fake binary classification**을 수행했습니다.

### 3. Model Comparison

MobileViT의 특성을 분석하기 위해 다른 딥러닝 기반 분류 모델과 성능을 비교했습니다.

주요 평가 지표로 **Accuracy, Precision, Recall, F1-score**를 활용했습니다.

---

## Tech Stack

**Programming**

* Python

**Deep Learning**

* MobileViT
* CNN
* Vision Transformer

**Data Processing**

* Image Processing
* Video Frame Extraction

**Evaluation**

* Accuracy
* Precision
* Recall
* F1-score
