# Nvidia-Isaac Sim & Isaac Lab Dev
Physical AI · Reinforcement Learning · JetBot Autonomous Driving

# 📌 Overview (프로젝트 개요)

This repository is dedicated to research and development in Physical AI, utilizing NVIDIA Isaac Sim and Isaac Lab. The final goal is to build a reinforcement-learning–based autonomous driving system using JetBot. The project focuses on implementing realistic physical phenomena to produce robust and reliable RL policies.

이 저장소는 NVIDIA Isaac Sim과 Isaac Lab 환경에서 Physical AI(물리현상 기반 AI)를 연구하는 공간입니다. 최종 목표는 JetBot 강화학습 기반 자율주행 시스템을 구축하는 것입니다. 실제 물리현상을 충실히 반영한 시뮬레이션을 통해 현실적이고 견고한 RL 정책을 만드는 것을 핵심 방향으로 합니다.

# 🎯 Final Goals (최종 목표)
### English
Build a realistic JetBot simulation in Isaac Sim, including acceleration, inertia, friction, braking, and collision characteristics
Develop RL environments in Isaac Lab (Line Tracking → Free Navigation)
Deploy trained RL policies to the real JetBot (ROS / Ubuntu 18.04)

### Korean
JetBot + Isaac Sim에서 가속·관성·마찰·제동·충돌을 모두 포함한 현실적 물리 시뮬레이션 구축
Isaac Lab 기반 강화학습 환경(Line Tracking → Free Navigation) 개발
학습된 정책을 실제 **JetBot(ROS/18.04)**에 업로드하여 자율주행 구현

# ✅ To-Do Roadmap (단계별 개발 로드맵)
### 1. Environment Setup (환경 구성)
EN: Set up Isaac Sim, Isaac Lab, CUDA, PyTorch, ROS, and all required development tools. 
KR: Isaac Sim, Isaac Lab, CUDA, PyTorch, ROS 및 필요 개발 도구 전체 환경을 구성합니다.

### 2. Repository Structure Design (저장소 구조 설계)
EN: Define workspace layout and development branches (main, dev-sim, dev-rl, sim2real, experiments).
KR: main, dev-sim, dev-rl, sim2real, experiments 등의 브랜치 및 워크스페이스 구조를 설계합니다.

### 3. Create MockRobot for Physics Tests (물리 실험용 MockRobot 생성)
EN: Build a simple box-shaped robot USD model for controlled physical experiments.
KR: 물리 환경 실험을 위해 단순한 박스 형태의 MockRobot USD를 생성합니다.

### 4. Physics Parameter Exploration (물리 파라미터 탐색)
EN: Experiment with mass, friction, inertia, damping, and motor torque to understand Isaac Sim physics.
KR: 질량, 마찰, 관성, 감쇠, 모터 토크 등 다양한 물리 요소를 실험합니다.

### 5. Basic Dynamics Testing (기초 동역학 실험)
EN: Test acceleration, deceleration, stopping distance, turning behavior, and collision responses.
KR: 가속, 감속, 정지 거리, 회전 반응, 충돌 반응을 실험합니다.

### 6. Import JetBot USD (JetBot 모델 불러오기)
EN: Load the official JetBot USD model and analyze its structure.
KR: 공식 JetBot USD 모델을 로드하고 구조를 분석합니다.

### 7. JetBot Physics Tuning (JetBot 물리 파라미터 튜닝)
EN: Tune mass, COM, wheel friction, damping, and motor characteristics to match real-world JetBot.
KR: 실제 JetBot과 유사하도록 질량, 무게 중심, 바퀴 마찰, 감쇠, 모터 특성을 조정합니다.

### 8. Default vs Tuned JetBot Comparison (기본 JetBot vs 튜닝 JetBot 비교)
### EN: Compare acceleration, braking, curvature handling, and stability between the two models.
KR: 두 모델의 가속, 제동, 곡선 주행, 안정성을 비교합니다.

### 9. Sensor Setup (센서 세팅)
EN: Configure camera, LiDAR (optional), IMU, and noise models. 
KR: 카메라, LiDAR(선택), IMU 및 노이즈 모델을 설정합니다.

### 10. Low-Level Controller Development (로우레벨 제어기 개발)
EN: Implement motor commands, safety limits, and PID-based steering and throttle control. 
KR: 모터 명령, 안전 제한, PID 조향·속도 제어기를 구현합니다.

### 11. RL Environment Wrapper (강화학습 환경 래퍼 구축)
EN: Implement reset(), step(), observation space, and action space using Isaac Lab.
KR: Isaac Lab 기반으로 reset(), step(), 관측/행동 공간을 구성합니다.

### 12. Line Tracking Environment (라인트래킹 환경 구현)
EN: Build a simple lane-following RL environment with a basic reward function.
KR: 기본 보상 함수를 가진 선형 트래킹 환경을 제작합니다.

### 13. PPO RL Training (PPO 기반 학습)
EN: Train a baseline PPO policy and evaluate performance.
KR: PPO 기본 정책을 학습시키고 성능을 평가합니다.

### 14. Curriculum Learning (커리큘럼 학습)
EN: Gradually increase difficulty: complex curves, branching paths, noise. 
KR: 난이도를 점진적으로 증가시키며 복잡한 곡선, 분기점, 노이즈 등을 추가합니다.

### 15. Obstacle Avoidance Expansion (장애물 회피 확장)
EN: Add an environment that handles obstacle detection and avoidance.
KR: 장애물 탐지 및 회피 기능을 포함한 환경을 추가합니다.

### 16. Domain Randomization (도메인 랜덤화)
EN: Randomize lighting, friction, mass, and camera noise for robustness. 
KR: 조명, 마찰, 질량, 카메라 노이즈 등 환경 변수를 무작위화합니다.

### 17. Large-Scale Parallel Training (대규모 병렬 학습)
EN: Increase environment count, tune training speed, and run hyperparameter sweeps. 
KR: 환경 수를 늘리고 학습 속도를 조정하며 다양한 하이퍼파라미터를 실험합니다.

### 18. Policy Optimization (정책 최적화)
EN: Visualize policy behavior, analyze failure cases, compress model with ONNX. 
KR: 정책 동작을 시각화하고 실패 사례를 분석하며 ONNX 등을 통해 모델을 경량화합니다.

### 19. Sim2Real Preparation (Sim2Real 준비)
EN: Export the final policy, build ROS inference nodes, and match sensor/actuator mapping. 
KR: 최종 정책을 내보내고 ROS 추론 노드를 구축하며 센서/액추에이터 매핑을 일치시킵니다.

### 20. Real JetBot Testing (실제 JetBot 테스트)
EN: Test JetBot with increasing difficulty: low-speed → controlled area → open area.
KR: JetBot을 저속 → 제한 구역 → 오픈 구역 순으로 점진적으로 테스트합니다.

### 22. Latency & Jitter Compensation (지연 및 지터 보정)
EN: Adjust for differences between simulation and real hardware timing.
KR: 시뮬레이터와 실제 하드웨어 간의 타이밍 차이를 보정합니다.

### 23. Final Sim2Real Evaluation (최종 Sim2Real 평가)
EN: Compare sim vs real behavior and iterate improvements.
KR: 시뮬레이션과 실제 성능을 비교하고 개선을 반복합니다.

### 24. Documentation & Automation (문서화 및 자동화)
EN: Write setup guides, experiment logs, and automated run scripts.
KR: 설정 가이드, 실험 로그, 자동 실행 스크립트 등을 문서화합니다.

### 25. Project Finalization & Future Work (프로젝트 마무리 & 향후 계획)
EN: Prepare final report, presentations, and outline possible extensions.
KR: 최종 보고서, 발표 자료를 준비하고 향후 확장 방향을 정리합니다.

# 🚀 Tech Stack (기술 스택)
- Isaac Sim 5.0.0
- Isaac Lab
- Python / PyTorch
- Reinforcement Learning (PPO 중심)
- ROS + JetBot

# 🔖 Tags
physical-ai
isaac-sim
isaac-lab
jetbot
reinforcement-learning
autonomous-driving
sim2real
