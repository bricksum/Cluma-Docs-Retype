---
label: Home
icon: home
---

# Cluma 기술 문서에 오신 것을 환영합니다

Cluma는 온프레미스 GPU 클러스터를 쉽게 관리하고, 인프라 운영자와 AI/ML 엔지니어가 빠르게 컨테이너 환경을 생성할 수 있는 플랫폼입니다.

---

## 문서 목차

| 섹션 | 설명 |
|------|------|
| [Getting Started](./getting-started/index.md) | 사전 요구사항, 핵심 개념, 빠른 시작 가이드 |
| [User Guide](./user-guide/index.md) | 컨테이너, 스토리지, 이미지 관리 |
| [Admin Guide](./admin-guide/index.md) | 사용자/그룹/레포지토리/클러스터/감사 로그 관리 |
| [Settings](./settings/index.md) | 프로필, 비밀번호, SSH Key 관리 |
| [Troubleshooting](./troubleshooting/index.md) | 자주 발생하는 오류 및 해결 방법 |
| [Release Notes](./release-notes/index.md) | 날짜별 변경 사항 |

---

## 대상 사용자

- 온프레미스 GPU 서버를 운영하는 인프라 운영자
- 인프라 지식 없이 GPU 환경이 필요한 AI/ML 엔지니어

---

## 주요 기능

### 계정 및 접근 관리

- 역할 기반 접근 제어: 관리자 / 일반 사용자 권한 분리
- 그룹 단위 리소스 할당 및 Kubernetes namespace 자동 생성
- SSH Key 등록 및 관리 (직접 입력 / 파일 업로드)
- 모든 주요 동작에 대한 감사 로그 기록 (관리자 조회 가능)

### GPU 개발 환경

- **인스턴스 카탈로그**: 노드 가용 자원 기반으로 자동 산정된 CPU/메모리 패키지에서 선택
- **템플릿 빠른 시작**: 자주 쓰는 설정을 템플릿으로 저장 → 한 번에 생성
- **표준 포트 자동 노출**: VS Code(8443) / SSH(22) / JupyterLab(8888) 포트가 자동으로 열려, 컨테이너 상세 페이지의 카드 버튼으로 즉시 접속
- **Pod 진단**: 컨테이너 상세에서 Phase / Node / Pod IP / Conditions / Events 실시간 조회
- **NUMA-aware CPU 할당**: 동일 NUMA 노드 내에서만 CPU 코어 선택 (고성능 워크로드용)
- 실시간 로그 조회 및 컨테이너 상태 관리

### 스토리지

- NFS, Local 등 StorageClass 선택하여 PVC 생성
- 그룹 내 스토리지 공유 및 컨테이너 마운트
- 스토리지 사용 현황(사용 중 / 최대 / 사용 가능) 실시간 표시

### 컨테이너 이미지 관리

- 멀티 레포지토리 등록 및 통합 관리
- 레포지토리 이미지 탐색 및 퍼블릭 이미지 직접 입력
- 사용자 커스텀 이미지 등록

### 리소스 모니터링

- **개인 대시보드**: CPU, 메모리, GPU, 스토리지 잔여량 (헤더 상단)
- **관리자 대시보드**: 전체/그룹별 리소스 사용량, 파이차트, 사용률 색상 강조(70% 노랑 / 90% 빨강)
- **클러스터 페이지**: 상태 · 분포 · 사용량 · 모니터링 · 스토리지 5개 탭으로 통합 조회
- **Grafana 외부 연동**: 시계열 그래프 (클러스터 페이지 → 모니터링 탭)

### 보안 격리

- 그룹 namespace에 **Pod Security Admission(`baseline`)** 자동 적용 → `hostNetwork` / `hostPort` / `privileged` 컨테이너 거부
- 그룹 namespace에 **NetworkPolicy** 자동 적용 → 그룹 간 네트워크 격리, 표준 포트만 외부 노출
- 사용자 데이터는 PostgreSQL RLS 기반 행 단위 권한 제어

### 클러스터 운영 관리 (관리자)

- 클러스터 노드 등록/수정 및 스케줄러 제외 (Drained)
- 노드 진단 (NetworkUnavailable / MemoryPressure / DiskPressure / PIDPressure)
- GPU 분할 사용 (MIG): 하나의 GPU를 여러 워크로드에 할당
- 컨테이너 이미지 레포지토리 등록 및 관리

---

## 지원 예정 기능

| 기능 | 시점 |
|---|---|
| Harbor 사설 레지스트리 통합 | v1.2 |
| 그룹 공유 스토리지 (NFS quota 기반) | v1.2 |
| InfiniBand 토폴로지 인지 스케줄링 | v1.2 |
| AI Agent 기반 운영 자동화 (리소스 추천 · 이상 탐지 · 유휴 회수) | 검토 |
| NPU / TPU 등 다양한 가속기 통합 관리 | 검토 |
| 멀티 클러스터 통합 뷰 | 검토 |
| 우선순위 큐잉 · 선점형 워크로드 · 시간 기반 스케줄링 | 검토 |
| 팀/사용자별 GPU 사용 시간 기반 비용 리포트 | 검토 |
| 수요 기반 GPU 오토스케일링 | 검토 |
| 모델 서빙 파이프라인 (원클릭 배포 · A/B 테스트 · 추론 오토스케일링) | 검토 |
| 전력 소비 모니터링 · 탄소 발자국 리포트 | 검토 |

---

## 다음 단계

- [사전 요구사항](./getting-started/prerequisites.md) — 설치 전 필요한 환경 조건
- [핵심 개념](./getting-started/concepts.md) — 유저, 그룹, 인스턴스, 컨테이너 등 Cluma 핵심 개념
- [사용자 빠른 시작](./getting-started/quickstart.md) — 컨테이너 생성까지 빠르게 시작하기
- [최신 변경 사항](./release-notes/index.md) — 날짜별 릴리스 노트
