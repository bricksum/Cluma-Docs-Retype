---
label: Home
icon: home
---

# Cluma 기술 문서에 오신 것을 환영합니다

Cluma는 온프레미스 GPU 클러스터를 쉽게 관리하고,
인프라 운영자와 AI/ML 엔지니어가 빠르게 컨테이너 환경을 생성할 수 있는 플랫폼입니다.
---

## 문서 목차

| 섹션 | 설명 |
|------|------|
| [Getting Started](./getting-started/index.md) | 사전 요구사항, 핵심 개념, 빠른 시작 가이드 |
| [User Guide](./user-guide/index.md) | 컨테이너, 스토리지, 이미지 관리 방법 |
| [Admin Guide](./admin-guide/index.md) | 사용자/그룹 관리, 클러스터 운영 |
| [Settings](./settings/index.md) | 프로필, 비밀번호, SSH Key 관리 |
| [Troubleshooting](./troubleshooting/index.md) | 자주 발생하는 오류 및 해결 방법 |

---

## 대상 사용자
- 온프레미스 GPU 서버를 운영하는 인프라 운영자
- 인프라 지식 없이 GPU 환경이 필요한 AI/ML 엔지니어

---

## Cluma 주요 기능

### 계정 및 접근 관리

- 역할 기반 접근 제어 : 관리자 / 일반 사용자 권한 분리
- 그룹 단위 리소스 할당 및 Kubernetes namespace 자동 생성
- SSH Key 등록 및 관리 (직접 입력 / 파일 업로드)

### GPU 개발 환경

- 원클릭 템플릿 또는 고급 설정으로 컨테이너 생성
- SSH, Jupyter, VSCode 등 포트포워딩 기반 다양한 접속 방식 지원
- Dynamic / Static 리소스 할당 방식 선택
- 실시간 로그 조회 및 컨테이너 상태 관리

### 스토리지

- NFS, Local 등 StorageClass 선택하여 PVC 생성
- 그룹 내 스토리지 공유 및 컨테이너 마운트
- 개인 전용 스토리지 분리 제공

### 컨테이너 이미지 관리

- 멀티 레포지토리 등록 및 통합 관리
- 레포지토리 이미지 탐색 및 퍼블릭 이미지 직접 입력
- 사용자 커스텀 이미지 등록

### 리소스 모니터링

- 개인 대시보드 : CPU, 메모리, GPU, 스토리지 현황
- 관리자 대시보드 : 전체 유저/그룹 리소스 사용량, 그룹별 필터
- 클러스터 대시보드 : 노드 상태, Pod 현황, 스케줄러 진단
- 클러스터 모니터링 : Grafana/Prometheus 기반 실시간 지표

### 클러스터 운영 관리 (관리자 전용)

- 클러스터 노드 등록/수정/활성화 : 노드 유형, GPU 모델, 역할(Control/Data Plane) 관리
- GPU 분할 사용 (MIG) : NVIDIA Multi-Instance GPU로 하나의 GPU를 여러 워크로드에 할당
- 컨테이너 이미지 레포지토리 등록 및 관리

---

## Cluma 지원 예정 기능

| 기능 | 설명 |
|---|---|
| AI Agent 기반 자동 운영 | 리소스 추천, 이상 탐지, 유휴 리소스 자동 회수 |
| NPU 지원 | GPU 외 NPU, TPU 등 다양한 AI 가속기 통합 관리 |
| 멀티 클러스터 | 여러 온프레미스 클러스터를 단일 뷰에서 통합 관리 |
| 스마트 스케줄링 | 우선순위 기반 큐잉, 선점형 워크로드, 시간 기반 스케줄링 |
| 리소스 비용 분석 | 팀/사용자별 GPU 사용 시간 기반 비용 리포트 |
| 워크로드 자동 스케일링 | 수요 기반 GPU 오토스케일링 |
| 모델 서빙 파이프라인 | 원클릭 모델 배포, A/B 테스트, 추론 오토스케일링 |
| 에너지 효율 관리 | 전력 소비 모니터링, 탄소 발자국 리포트 |

---

## 다음 단계

- [사전 요구사항 확인](./getting-started/prerequisites.md) — 설치 전 필요한 환경 조건
- [핵심 개념](./getting-started/concepts.md) — 유저, 그룹, 컨테이너 등 Cluma 핵심 개념
- [사용자 빠른 시작](./getting-started/quickstart.md) — 컨테이너 생성까지 빠르게 시작하기
