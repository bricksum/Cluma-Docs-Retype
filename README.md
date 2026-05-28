# Cluma Docs

> Cluma GPU 클러스터 관리 플랫폼 공식 기술 문서

## 🔗 문서 사이트

**[https://bricksum.github.io/Cluma-Docs-Retype](https://bricksum.github.io/Cluma-Docs-Retype)**

## 📋 문서 구조

```
CLUMA-DOCS-RETYPE/
├── index.md                          # 홈 (Cluma 소개 + 주요 기능 + 지원 예정 기능)
│
├── getting-started/
│   ├── index.md                      # 시작 가이드 진입점
│   ├── concepts.md                   # 핵심 개념 (유저/그룹/인스턴스/컨테이너/스토리지/이미지/MIG/보안격리/감사로그)
│   ├── prerequisites.md              # 사전 요구사항 (K8s 버전, StorageClass, GPU 드라이버 등)
│   ├── quickstart.md                 # 사용자 빠른 시작 (6단계)
│   └── admin-setup.md                # 관리자 초기 설정 (4단계)
│
├── user-guide/
│   ├── index.md                      # 사용자 가이드 개요
│   ├── container.md                  # 컨테이너 2-step 생성, 템플릿, Pod 진단, 접속 카드
│   ├── storage.md                    # 스토리지 생성/마운트/공유 방법
│   └── image.md                      # 커스텀 이미지 등록 및 레지스트리 탐색 + base image 가이드
│
├── admin-guide/
│   ├── index.md                      # 관리자 가이드 개요
│   ├── dashboard.md                  # 관리자 대시보드 (그룹별 사용량 통합)
│   ├── user-management.md            # 사용자 생성/수정/삭제, 역할 설정
│   ├── group-management.md           # 그룹 생성/수정/삭제, 리소스 할당
│   ├── registry-management.md        # 컨테이너 이미지 레포지토리 등록 및 관리
│   ├── cluster.md                    # 클러스터 상태/분포/사용량/모니터링/스토리지 5탭 통합
│   └── audit-logs.md                 # 감사 로그 조회 및 필터링
│
├── settings/
│   └── index.md                      # 프로필 정보, 비밀번호 변경, SSH Key 관리
│
├── troubleshooting/
│   └── index.md                      # 자주 발생하는 오류 및 해결 방법
│
├── release-notes/
│   ├── index.md                      # 날짜별 릴리스 노트 목차
│   └── 2026-05-29.md                 # v1.1.0 — 표준 포트, Pod 진단, 보안 격리, 인스턴스 카탈로그
│
├── retype.yml                        # Retype 사이트 설정
└── .github/workflows/retype.yml      # GitHub Pages 자동 배포
```

## 🛠 로컬 미리보기

```bash
# Retype CLI 설치 (Node.js 필요)
npm install -g retypeapp

# 로컬 서버 실행
retype watch
```

## 📝 기여

- 컨테이너/스토리지/이미지/감사 로그 사용 흐름이 바뀔 때마다 해당 페이지를 갱신합니다.
- 신규 기능은 `release-notes/YYYY-MM-DD.md` 형태의 파일을 추가하고 `release-notes/index.md`의 목차 표에 한 행을 추가합니다.
- 화면 캡처는 `static/` 디렉토리에 배치합니다.
