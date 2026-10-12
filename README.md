
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F1689,100:326CE5&fontColor=FFFFFF&height=200&text=Duhwan%20Park&fontSize=42&fontAlignY=36&desc=DevOps%20%7C%20MLOps%20Platform%20Engineer&descSize=18&descAlignY=56" width="100%" />
</div>

## About Me

**AI 서비스가 안정적으로 배포되고 운영될 수 있는 인프라와 플랫폼을 구축합니다.**

의료 AI 추론 서비스의 **DevOps · MLOps Platform Engineer**로 일하고 있습니다.

Docker Compose 기반 수동 운영 환경을 **Kubernetes(K3s) · Helm · ArgoCD 기반 GitOps 플랫폼**으로 단계적으로 전환하고, 개발자가 직접 배포할 수 있는 Internal Developer Platform과 통합 Observability 환경을 구축하고 있습니다.

최근에는 AI 라이브러리와 서빙 저장소의 **PR CI 검증 체계를 표준화**하고, 모델 구성 검증부터 Release · Deployment · Delivery까지 이어지는 운영 구조를 설계하고 있습니다.

FastAPI 백엔드와 React 프론트엔드 개발로 시작해 현재는 **CI/CD · 플랫폼 자동화 · AI 추론 인프라 운영 안정성**에 집중하고 있습니다.

`DevOps` `MLOps` `Platform Engineering` `Kubernetes` `GitOps` `CI/CD` `Observability` `AI Serving`

---

## What I Do

### 1. Kubernetes · GitOps Platform

**SSH 기반 수동 배포를 Git 기반 선언형 운영으로 단계적으로 전환**

- K3s 기반 Kubernetes 클러스터 구축 및 GPU 워커 운영
- Helm Chart와 values 기반 서비스별 배포 구조 표준화
- ArgoCD를 통한 Git 기반 배포·동기화 및 변경 이력 관리
- Ingress · cert-manager · 내부 DNS 기반 서비스 접근 및 TLS 구성
- SOPS + age를 활용한 Secret 암호화 관리
- Control Plane과 플랫폼 컴포넌트를 GPU 워커에서 분리해 장애 영향 범위 축소 (이전 중 서비스별 공백 약 10~90초)

### 2. CI/CD · Release Engineering

**다중 저장소의 코드·모델 구성 검증을 표준화하고 릴리스와 배포의 책임을 분리**

**PR CI — 구현 및 단계적 적용**

- GitHub Actions 기반 공통 PR CI 구성
- AI 라이브러리 · 서빙 관련 **5개 저장소**의 검증 체계 정비
- 변경 파일 경로에 따라 필요한 검사만 선택적으로 실행
- Unit Test · Lint · Package · Public API · Model Manifest 정합성 검사 구성
- 개별 검증 Job의 결과를 단일 Check로 집계
- report-only 관찰 후 기준 충족 시 Required Check로 단계적 승격 (2개 저장소 완료 · 첫 저장소 PR 25건에서 CI 무관 실패 0건)

**Release Engineering — 설계 진행 중**

- PR CI와 Release CI의 검증 책임 분리
- 라이브러리 버전 · 모델 구성 · 릴리스 산출물 정합성 관리 구조 설계
- Release · Deployment · Delivery 이력과 책임 구분
- 사내 GitOps 배포와 외부 환경 전달 흐름 분리

### 3. Internal Developer Platform

**특정 담당자에게 의존하던 수동 배포를 Self-Service 포털로 전환**

- FastAPI 기반 사내 배포 포털 설계·개발
- 이미지 · 배포 대상 · 환경 설정 입력 → Git 커밋 → ArgoCD Sync 연계
- GitHub App 기반 배포 요청과 변경 이력 추적
- Registry v2 API 직접 조회로 실제 배포 가능한 이미지 확인
- 브라우저 내 age 암호화 기반 Secret 입력 흐름 구현
- 배포 버전 · 상태 · 변경 이력을 확인하는 Audit Trail 구성

### 4. Observability · Incident Response

**Metrics · Logs · Traces를 연결해 AI 추론 서비스의 장애 원인을 단계적으로 분석**

- Prometheus · Loki · Tempo · Grafana · Alloy 기반 통합 관측 환경 구축
- OpenTelemetry 기반 Metrics · Logs · Traces 수집 체계 구성
- Triton BLS 파이프라인의 하위 8개 모델 호출을 단일 Trace로 연결
- Workload → Pod → Node → GPU 단계별 운영 대시보드 구축
- GPU OOM · DiskPressure · Docker/K3s 런타임 자원 충돌 분석
- 관측·관리 컴포넌트를 GPU 워커에서 분리해 워커 장애 시에도 관리 화면과 기존 관측 데이터에 접근할 수 있도록 구성

### 5. MLOps · AI Inference Infrastructure

**GPU · 모델 구성 · 컨테이너 · 네트워크 제약을 고려한 의료 AI 추론 서비스 운영**

- 국내 종합병원 온프레미스 서버 7대 설치·구성 참여
- NVIDIA Triton Inference Server 기반 의료 AI 추론 워크로드 운영
- GPU 메모리 사용량과 컨테이너 자원 충돌 분석 및 배치 제약 관리
- 모델 Manifest와 실제 서빙 구성 간 정합성 검증 체계 정비
- 제한된 네트워크 환경을 고려한 이미지 전달·배포 절차 구성
- 대용량 추론 이미지의 Registry 간 전달 자동화
- Python Backend 장애 분석 및 Core Dump 수집 체계 정비

---

## Tech Stack

### Platform · DevOps

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![K3s](https://img.shields.io/badge/K3s-FFC61C?style=for-the-badge&logo=k3s&logoColor=black)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)
![ArgoCD](https://img.shields.io/badge/Argo_CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![SOPS](https://img.shields.io/badge/SOPS-555555?style=for-the-badge&logoColor=white)

### Observability

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Loki](https://img.shields.io/badge/Loki-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Tempo](https://img.shields.io/badge/Tempo-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=for-the-badge&logo=opentelemetry&logoColor=white)

### MLOps · AI Serving

![Triton](https://img.shields.io/badge/Triton_Inference_Server-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![NVIDIA GPU](https://img.shields.io/badge/NVIDIA_GPU-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)

### Backend · Frontend

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

### Cloud

![AWS ECR](https://img.shields.io/badge/AWS_ECR-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![AWS Amplify](https://img.shields.io/badge/AWS_Amplify-FF9900?style=for-the-badge&logo=awsamplify&logoColor=white)

---

## Experience

| 기간 | 소속 | 역할 |
|---|---|---|
| 2025.10 ~ 현재 | 연세대학교 의료원 산학협력단 | DevOps · MLOps Platform Engineering — K3s · GitOps · CI/CD · Observability |
| 2025.07 ~ 2025.10 | ONTACT HEALTH (인턴) | Full-Stack Development — AI 챗봇 · 보험 약관 분석 AI Agent |

---

## How I Work

- **AI 에이전트가 일하는 환경을 설계합니다.** — 작업 규칙은 Skill로, 맥락은 Daily Log로 Git에 관리하고, 검토한 내용만 프로젝트 문서로 올려 AI가 세션이 바뀌어도 같은 기준과 맥락으로 이어 가게 합니다.
- **장애는 증상보다 원인을 찾습니다.** — 로그 · 지표 · Trace를 연결해 Workload부터 Node · GPU까지 원인을 좁힙니다.
- **시스템의 기준 데이터는 명확해야 합니다.** — 배포할 상태는 Git, 실제 반영 상태는 ArgoCD, 이미지는 Registry를 기준으로 삼아 정보가 어긋나지 않게 관리합니다.
- **반복 작업은 자동화합니다.** — 수동 배포와 검증 절차를 CI · GitOps 파이프라인으로 옮겨 사람이 직접 처리하는 단계를 줄입니다.

---

## Contact

- **Email:** [enghksqkr05@gmail.com](mailto:enghksqkr05@gmail.com)
- **Blog:** [https://duhwan98.tistory.com](https://duhwan98.tistory.com)
