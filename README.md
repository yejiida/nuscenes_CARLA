# nuscenes_CARLA
# 🚗 Autonomous Driving Mini Projects with nuScenes & CARLA

이 레포지토리는 nuScenes 데이터셋과 CARLA 시뮬레이터를 활용하여 자율주행 분야의 핵심 기술들을 소규모 프로젝트로 실습한 결과물을 모아둔 것입니다.  
실제 현업에서 다루는 perception → prediction → planning 과정을 일부 체험해보고자 공부한 내용을 바탕으로 구성되었습니다.

---
**공부한 내용들 추후  천천히 업데이트 예정**

## 📌 Project List

### 1. Object Detection & Tracking
- **Goal:** nuScenes의 카메라/LiDAR 데이터를 활용하여 차량, 보행자 등의 객체를 탐지하고 추적
- **Tasks:**
  - 2D Object Detection (YOLOv8 / Faster R-CNN)
  - 3D Object Detection (PointPillars, CenterPoint)
  - Kalman Filter / SORT / DeepSORT 기반 Tracking
- **Output:** 객체 Bounding Box + Tracking ID 시각화

---

### 2. Lane & Road Segmentation
- **Goal:** 도로와 차선 영역을 분할(segmentation)하여 주행 가능한 영역 파악
- **Tasks:**
  - nuScenes 카메라 데이터에서 차선/도로 영역 세그멘테이션 (DeepLabv3+, SegFormer)
  - Class imbalance 처리 및 mIoU 성능 비교
- **Output:** 시각화된 차선 영역 (예: 파란색=차선, 녹색=도로)

---

### 3. Sensor Fusion for Perception
- **Goal:** 카메라 + LiDAR + RADAR 데이터를 융합하여 더 정확한 객체 인식
- **Tasks:**
  - 데이터 시간 동기화 (timestamp alignment)
  - LiDAR point cloud + camera 2D detection late-fusion
  - RADAR 속도 정보와 결합하여 상대 차량 속도 추정
- **Output:** Fusion 기반 객체 detection 성능 비교

---

### 4. Trajectory Prediction
- **Goal:** 보행자와 차량의 미래 움직임을 예측하여 잠재적인 충돌 위험 탐지
- **Tasks:**
  - Past trajectory 데이터셋 구성
  - LSTM / Transformer 기반 trajectory forecasting
  - Metrics: ADE (Average Displacement Error), FDE (Final Displacement Error)
- **Output:** 예측된 궤적을 Ground Truth와 비교 시각화

---

### 5. Motion Planning with CARLA
- **Goal:** 인지(perception) 결과를 활용해 CARLA 시뮬레이터에서 안전한 주행 경로 생성
- **Tasks:**
  - nuScenes dataset 기반 인지 모델을 CARLA에 연결
  - MPC (Model Predictive Control) 기반 경로 계획
  - Fail-safe: 센서 손실/오류 상황 시 fallback 경로 생성
- **Output:** CARLA 시뮬레이터에서 주행 영상 및 주행 로그

---

## 📂 Repository Structure
```bash
├── README.md
