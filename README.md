# Oral-Medication-Image-Object-Detection-Project

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Colab](https://img.shields.io/badge/Google%20Colab-supported-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![YOLOv8](https://img.shields.io/badge/Model-YOLOv8m-00A67D)](https://docs.ultralytics.com/)

> Detect pills in medication photos and prepare the data pipeline for YOLOv8 training.

## Overview

This project is a healthcare object detection mission focused on oral medication images.
The goal is to detect up to four pills in a photo and build a reliable pipeline for training and comparing detection models.

### What this repo contains

- Data inspection notebooks
- Annotation cleaning and preprocessing
- Multi-label stratified train/validation split
- COCO to YOLO format conversion
- YOLOv8m training notebook
- Project report PDFs

## Current Project Status

The notebooks show a complete preparation workflow and a YOLOv8m training setup.

### Dataset summary from the notebook

- Classes: 73
- Train images: 1,182
- Validation images: 307
- Image size: 976 x 1280
- Split strategy: Multi-label stratified split

### Modeling notes

- Base model: YOLOv8m
- Pretrained weights: `yolov8m.pt`
- Input format: YOLO normalized bounding boxes
- Training image size: 1280
- Optimizer: AdamW
- Epochs: 50

## Results & Notes

The repository currently documents the training plan and preprocessing workflow more than final benchmark numbers.

### Verified in the notebooks

- Class distribution analysis
- Invalid bounding box removal
- Category remapping
- Train/validation split
- COCO to YOLO conversion
- Symbolic-link based dataset structure

### Still to emphasize in the README

- Final validation metrics
- Kaggle submission score
- Best checkpoint comparison
- Error analysis by class or pill size

### Results Preview

| Item | What it shows | Source |
| --- | --- | --- |
| Class distribution | How evenly the 73 classes are represented | `oral_medication.ipynb` |
| Pills per image | Whether the dataset matches the "up to 4 pills" task | `oral_medication.ipynb` |
| Bounding box area | Small-object difficulty and scale distribution | `oral_medication.ipynb` |
| Sample image overlay | Visual QA for annotation quality | `oral_medication.ipynb` |
| YOLOv8m setup | Baseline model choice and training config | `YOLOv8m_best.ipynb` |

## Workflow

1. Check file existence and dataset structure
2. Inspect class distribution
3. Remove invalid bounding boxes
4. Remap category IDs
5. Split train/validation sets with multi-label stratification
6. Save processed annotations
7. Convert COCO format to YOLO format
8. Use symbolic links to avoid copying image files
9. Train and compare YOLOv8m models

## Notebooks

| File | Purpose |
| --- | --- |
| `oral_medication.ipynb` | Data checking and preprocessing |
| `YOLOv8m_best.ipynb` | YOLOv8m training setup |
| `최종 노트북파일.ipynb` | Final notebook version |

## Reports

| File | Purpose |
| --- | --- |
| `Oral-Medication-Image-Object-Detection-Project_report.pdf` | Project report |
| `20260330_tomas_yolo8m_v3.pdf` | Additional report / experiment document |

## Tech Stack

- Python
- PyTorch
- TorchVision
- Ultralytics YOLOv8
- Pandas
- OpenCV
- Matplotlib
- Seaborn
- Google Colab

## Key Notebook Highlights

### Data inspection

- File presence checks
- Basic dataset structure checks
- Class distribution plots

### Preprocessing

- Remove invalid bounding boxes
- Remap category IDs
- Keep original resolution instead of letterbox resize
- Perform train/validation split

### Data loading

- Convert COCO `[x, y, w, h]` to YOLO `[x_center, y_center, w, h]`
- Build directory structure with symbolic links
- Prepare the data pipeline for YOLO training

### YOLOv8m training setup

- Model: YOLOv8m
- Pretrained weights: `yolov8m.pt`
- Batch size: 16
- Learning rate: 0.001
- Early stopping: `patience=20`
- Checkpoint storage: Google Drive

## Roadmap

- Add final evaluation numbers to the README
- Include sample inference images
- Document the best checkpoint and comparison results
- Summarize class-level failure cases

## License

MIT License. See [LICENSE](LICENSE) for details.

---

# 구강 복용 약물 이미지 객체 탐지 프로젝트

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Colab](https://img.shields.io/badge/Google%20Colab-supported-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![YOLOv8](https://img.shields.io/badge/Model-YOLOv8m-00A67D)](https://docs.ultralytics.com/)

> 복용 약 사진에서 알약을 탐지하고 YOLOv8 학습 파이프라인을 준비하는 프로젝트입니다.

## 개요

이 프로젝트는 구강 복용 약물 이미지에 대한 헬스케어 객체 탐지 미션입니다.
한 장의 사진에서 최대 4개의 알약을 탐지하고, 안정적인 학습 및 비교가 가능한 데이터 파이프라인을 만드는 것이 목표입니다.

### 저장소 구성

- 데이터 확인용 노트북
- 어노테이션 정리 및 전처리
- 다중 라벨 기반 train/validation 분리
- COCO to YOLO 변환
- YOLOv8m 학습 노트북
- 프로젝트 보고서 PDF

## 현재 상태

이 저장소는 최종 성능 수치보다 전처리와 학습 준비 과정을 자세히 담고 있습니다.

### 노트북에서 확인되는 데이터 요약

- 클래스 수: 73
- Train 이미지: 1,182장
- Validation 이미지: 307장
- 이미지 크기: 976 x 1280
- 분할 방식: Multi-label stratified split

### 모델 설정

- 기준 모델: YOLOv8m
- 사전학습 가중치: `yolov8m.pt`
- 입력 포맷: YOLO 정규화 바운딩 박스
- 학습 이미지 크기: 1280
- 옵티마이저: AdamW
- 에폭: 50

## 결과 및 메모

현재 README는 최종 점수보다 전처리 및 학습 구성에 초점을 둡니다.

### 노트북에서 확인된 내용

- 클래스 분포 분석
- 비정상 바운딩 박스 제거
- category 재매핑
- train/validation 분할
- COCO to YOLO 변환
- 심볼릭 링크 기반 데이터 구조

### README에 추가하면 좋은 항목

- 최종 검증 지표
- Kaggle 제출 점수
- 최고 체크포인트 비교
- 클래스별 실패 사례 분석

## 작업 흐름

1. 파일 존재 여부와 데이터 구조 확인
2. 클래스 분포 확인
3. 비정상 바운딩 박스 제거
4. category ID 재매핑
5. 다중 라벨 기반 train/validation 분할
6. 전처리된 어노테이션 저장
7. COCO를 YOLO 형식으로 변환
8. 이미지 파일은 심볼릭 링크로 구성
9. YOLOv8m 학습 및 비교

## 노트북

| 파일 | 용도 |
| --- | --- |
| `oral_medication.ipynb` | 데이터 확인 및 전처리 |
| `YOLOv8m_best.ipynb` | YOLOv8m 학습 설정 |
| `최종 노트북파일.ipynb` | 최종 노트북 버전 |

## 보고서

| 파일 | 용도 |
| --- | --- |
| `Oral-Medication-Image-Object-Detection-Project_report.pdf` | 프로젝트 보고서 |
| `20260330_tomas_yolo8m_v3.pdf` | 추가 보고서 / 실험 문서 |

## 사용 기술

- Python
- PyTorch
- TorchVision
- Ultralytics YOLOv8
- Pandas
- OpenCV
- Matplotlib
- Seaborn
- Google Colab

## 핵심 포인트

### 데이터 확인

- 파일 존재 여부 확인
- 기본 데이터 구조 확인
- 클래스 분포 시각화

### 전처리

- 비정상 바운딩 박스 제거
- category ID 재매핑
- letterbox 대신 원본 해상도 유지
- train/validation 분할

### 데이터 로딩

- COCO `[x, y, w, h]`를 YOLO `[x_center, y_center, w, h]`로 변환
- 심볼릭 링크로 디렉토리 구조 구성
- YOLO 학습용 데이터 파이프라인 준비

### YOLOv8m 학습 설정

- 모델: YOLOv8m
- 사전학습 가중치: `yolov8m.pt`
- 배치 크기: 16
- 학습률: 0.001
- Early stopping: `patience=20`
- 체크포인트 저장: Google Drive

## 다음 단계

- 최종 평가 수치를 README에 추가
- 추론 예시 이미지 추가
- 최고 체크포인트와 비교 결과 정리
- 클래스별 실패 사례 요약

## 라이선스

MIT License입니다. 자세한 내용은 [LICENSE](LICENSE)를 확인하세요.
