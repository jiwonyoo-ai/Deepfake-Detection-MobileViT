# Deepfake Detection with MobileViT

> A deepfake image and video detection system based on MobileViT, with comparative analysis against deep learning models.

딥페이크 이미지 및 영상에서 나타나는 시각적 특징을 분석하고, **MobileViT 기반 분류 모델을 활용하여 딥페이크 여부를 판별하는 시스템**입니다.

본 프로젝트에서는 CNN 기반 모델과 Vision Transformer 계열의 장점을 결합한 MobileViT를 적용하고, 기존 딥러닝 모델과의 비교를 통해 **딥페이크 탐지 성능과 경량화 모델의 활용 가능성**을 분석했습니다.

---

## Project Overview

### Motivation

생성형 AI 기술의 발전으로 실제 이미지와 구분하기 어려운 딥페이크 콘텐츠가 증가하면서, 이미지 및 영상의 진위 여부를 자동으로 판별하는 기술의 중요성이 높아지고 있습니다.

딥페이크 탐지 모델은 높은 분류 성능뿐만 아니라 실제 서비스 환경에서 활용하기 위한 **효율적인 추론 및 경량화**도 중요합니다.

본 프로젝트에서는 CNN의 지역적 특징 추출 능력과 Transformer의 전역적인 정보 처리 능력을 결합한 **MobileViT**를 활용하여 딥페이크 탐지 모델을 구현하고, 다른 딥러닝 모델과의 비교 분석을 수행했습니다.

---

## Objectives

* 딥페이크 이미지 및 영상 데이터 분석
* 딥페이크 탐지를 위한 이미지 전처리 및 분류 pipeline 구축
* MobileViT 기반 딥페이크 탐지 모델 구현
* 기존 딥러닝 모델과의 성능 비교
* 모델별 성능 차이 분석
* 경량 Vision 모델의 딥페이크 탐지 활용 가능성 분석

---

## System Pipeline

```text id="qz6n6q"
Deepfake Image / Video
        ↓
Frame / Image Extraction
        ↓
Preprocessing
        ↓
Train / Validation / Test Split
        ↓
Deep Learning Model
        ↓
Classification
        ↓
Real / Fake
        ↓
Performance Comparison
```

---

## Workflow

### 1. Data Preparation

딥페이크 이미지 및 영상 데이터를 모델 학습과 평가에 활용할 수 있도록 전처리했습니다.

영상 데이터의 경우 프레임 단위의 이미지를 추출하여 이미지 classification 방식으로 처리할 수 있도록 구성했습니다.

---

### 2. Image Preprocessing

입력 이미지를 모델의 입력 형식에 맞게 전처리하고, 학습 과정에서 사용할 수 있도록 데이터셋을 구성했습니다.

```text id="x0m7tb"
Input Image
    ↓
Resize
    ↓
Normalization
    ↓
Tensor Conversion
    ↓
Model Input
```

---

### 3. MobileViT

본 프로젝트에서는 **MobileViT**를 딥페이크 탐지 모델로 활용했습니다.

MobileViT는 CNN과 Vision Transformer의 구조적 장점을 결합하여 이미지의 지역적인 특징과 전역적인 정보를 함께 처리할 수 있도록 설계된 경량 Vision architecture입니다.

CNN을 통해 local representation을 추출하고 Transformer 구조를 통해 보다 넓은 범위의 feature relationships를 학습하는 방식으로 구성됩니다.

---

### 4. Deepfake Classification

전처리된 이미지를 모델에 입력하여 해당 이미지가 실제 이미지인지 딥페이크 이미지인지 분류합니다.

```text id="f9j3a7"
Input Image
      ↓
Feature Extraction
      ↓
MobileViT
      ↓
Classification Head
      ↓
Real / Fake
```

---

### 5. Comparative Analysis

MobileViT의 성능을 확인하기 위해 다른 딥러닝 기반 모델과 비교 분석을 수행했습니다.

모델별 classification performance를 비교하여 MobileViT의 성능과 특성을 분석했습니다.

---

## Model Architecture

### MobileViT

MobileViT는 CNN 기반의 local feature extraction과 Transformer 기반의 global representation learning을 결합한 구조입니다.

```text id="w8i3du"
Input Image
     ↓
Convolution
     ↓
Local Representation
     ↓
Transformer
     ↓
Global Representation
     ↓
Fusion
     ↓
Classification
```

이를 통해 CNN의 효율적인 feature extraction과 Transformer의 전역 정보 처리 특성을 함께 활용했습니다.

---

## Core Technologies

### MobileViT

MobileViT를 딥페이크 이미지 분류 backbone으로 활용했습니다.

경량화된 구조를 통해 일반적인 Vision Transformer 계열 모델보다 효율적인 이미지 처리 가능성을 고려했습니다.

---

### Deep Learning-based Classification

딥페이크와 실제 이미지를 구분하는 binary classification 문제로 구성하여 모델의 탐지 성능을 비교했습니다.

---

## Experimental Setup

| Component      | Description                   |
| -------------- | ----------------------------- |
| Task           | Deepfake Image Classification |
| Model          | MobileViT                     |
| Input          | Image / Video Frames          |
| Classification | Real / Fake                   |
| Framework      | Deep Learning                 |
| Language       | Python                        |

---

## Results

모델별 classification performance를 비교하여 MobileViT 기반 딥페이크 탐지 모델의 성능을 분석했습니다.

주요 분석 항목:

* Classification Accuracy
* Precision
* Recall
* F1-score
* Model performance comparison

---

## My Contributions

* 딥페이크 탐지 프로젝트 기획
* 딥페이크 이미지 및 영상 데이터 전처리
* MobileViT 기반 딥페이크 classification pipeline 구현
* 딥러닝 모델 학습 및 평가
* 모델별 classification performance 비교
* 실험 결과 분석 및 모델 특성 비교
* 딥페이크 탐지 시스템 구현

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

---

## Key Takeaways

본 프로젝트를 통해 **Vision model을 활용한 딥페이크 탐지 pipeline을 구현하고, 서로 다른 딥러닝 모델의 성능을 비교·분석하는 경험**을 수행했습니다.

특히 CNN과 Transformer의 특성을 결합한 MobileViT를 적용하여 **경량 Vision architecture의 딥페이크 탐지 활용 가능성**을 탐구했습니다.



![이미지1](./images/image1.jpg)  

![이미지2](./images/image2.jpg)  

![이미지3](./images/image3.jpg)  

![이미지4](./images/image4.jpg)  

![이미지5](./images/image5.jpg)  

![이미지6](./images/image6.jpg)  

![이미지7](./images/image7.jpg)  

