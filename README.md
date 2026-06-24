# Oral-Medication-Image-Object-Detection-Project

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Colab](https://img.shields.io/badge/Google%20Colab-supported-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![YOLOv8](https://img.shields.io/badge/Model-YOLOv8m-00A67D)](https://docs.ultralytics.com/)

> Detect pills in medication photos and prepare a training pipeline for YOLOv8 experiments.

## Overview

This project is a healthcare object detection mission focused on oral medication images.
The goal is to detect up to four pills in a photo and build a reliable pipeline for preprocessing, training, and comparison.

### What this repo contains

- Data inspection notebooks
- Annotation cleaning and preprocessing
- Multi-label stratified train/validation split
- COCO to YOLO format conversion
- YOLOv8m training notebook
- Project report PDFs

## Results & Notes

The current materials emphasize the preprocessing pipeline and YOLOv8m training setup.
No final benchmark table is exposed in the extracted report text, so this README focuses on the verified experiment configuration and dataset summary.

### Verified results and experiment facts

| Item | Value | Source |
| --- | --- | --- |
| Classes | 73 | Notebook / report materials |
| Train images | 1,182 | Notebook / report materials |
| Validation images | 307 | Notebook / report materials |
| Image size | 976 x 1280 | Notebook / report materials |
| Split strategy | Multi-label stratified split | Notebook |
| Base model | YOLOv8m | Notebook |
| Pretrained weights | `yolov8m.pt` | Notebook |
| Input format | YOLO normalized bounding boxes | Notebook |
| Epochs | 50 | Notebook |
| Batch size | 16 | Notebook |
| Optimizer | AdamW | Notebook |
| Learning rate | 0.001 | Notebook |
| Early stopping | `patience=20` | Notebook |

### What is currently verified in the notebooks

- Class distribution analysis
- Invalid bounding box removal
- Category remapping
- Train/validation split
- COCO to YOLO conversion
- Symbolic-link based dataset structure
- YOLOv8m baseline training setup

### What still belongs in a future report update

- Final validation metrics
- Kaggle submission score
- Best checkpoint comparison
- Error analysis by class or pill size
- Sample inference images

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
| `Oral-Medication-Image-Object-Detection-Project_report.pdf` | Report placeholder in this repo snapshot |
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

> 복용 약 사진에서 알약을 탐지하고 YOLOv8 실험 파이프라인을 준비하는 프로젝트입니다.

## 개요

이 프로젝트는 구강 복용 약물 이미지에 대한 헬스케어 객체 탐지 미션입니다.
한 장의 사진에서 최대 4개의 알약을 탐지하고, 전처리와 학습, 비교가 가능한 파이프라인을 만드는 것이 목표입니다.

### 저장소 구성

- 데이터 확인용 노트북
- 어노테이션 정리 및 전처리
- 다중 라벨 기반 train/validation 분리
- COCO to YOLO 변환
- YOLOv8m 학습 노트북
- 프로젝트 보고서 PDF

## 결과 및 메모

현재 자료는 최종 성능표보다 전처리 파이프라인과 YOLOv8m 학습 설정을 중심으로 구성되어 있습니다.
추출 가능한 보고서 텍스트에서는 최종 benchmark 표가 확인되지 않아, 이 README는 검증된 설정과 데이터 요약을 중심으로 정리했습니다.

### 검증된 결과 및 실험 정보

| 항목 | 값 | 출처 |
| --- | --- | --- |
| 클래스 수 | 73 | 노트북 / 보고서 자료 |
| Train 이미지 | 1,182장 | 노트북 / 보고서 자료 |
| Validation 이미지 | 307장 | 노트북 / 보고서 자료 |
| 이미지 크기 | 976 x 1280 | 노트북 / 보고서 자료 |
| 분할 방식 | Multi-label stratified split | 노트북 |
| 기준 모델 | YOLOv8m | 노트북 |
| 사전학습 가중치 | `yolov8m.pt` | 노트북 |
| 입력 포맷 | YOLO 정규화 바운딩 박스 | 노트북 |
| 에폭 | 50 | 노트북 |
| 배치 크기 | 16 | 노트북 |
| 옵티마이저 | AdamW | 노트북 |
| 학습률 | 0.001 | 노트북 |
| Early stopping | `patience=20` | 노트북 |

### 노트북에서 확인된 내용

- 클래스 분포 분석
- 비정상 바운딩 박스 제거
- category 재매핑
- train/validation 분리
- COCO to YOLO 변환
- 심볼릭 링크 기반 데이터 구조
- YOLOv8m 기준 학습 설정

### 앞으로 추가하면 좋은 내용

- 최종 검증 지표
- Kaggle 제출 점수
- 최고 체크포인트 비교
- 클래스별 실패 사례 분석
- 추론 예시 이미지

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
| `Oral-Medication-Image-Object-Detection-Project_report.pdf` | 보고서 스냅샷 / 자리표시 파일 |
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
