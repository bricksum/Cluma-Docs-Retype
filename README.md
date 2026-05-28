# Cluma Docs

> Cluma — 사내 GPU 클러스터 관리 플랫폼 공식 기술 문서

## 🔗 문서 사이트

**[https://bricksum.github.io/Cluma-Docs-Retype](https://bricksum.github.io/Cluma-Docs-Retype)**

## 📋 문서 구조

```
CLUMA-DOCS-RETYPE/
├── index.md                          # 홈 (Cluma 소개 + 주요 기능)
│
├── getting-started/
│   ├── index.md                      # 시작 가이드 진입
│   ├── concepts.md                   # 핵심 개념 — 모든 용어 정의의 SSOT
│   ├── prerequisites.md              # 사전 요구사항 (Kubernetes, 스토리지, GPU 드라이버)
│   ├── quickstart.md                 # 사용자 빠른 시작 (6단계)
│   └── admin-setup.md                # 관리자 초기 설정 (4단계)
│
├── user-guide/
│   ├── index.md                      # 사용자 가이드 개요
│   ├── container.md                  # 컨테이너 2단계 만들기, 템플릿, Pod 진단, 접속 카드
│   ├── storage.md                    # 스토리지 만들기와 마운트
│   └── image.md                      # 이미지 등록과 권장 base 이미지
│
├── admin-guide/
│   ├── index.md                      # 관리자 가이드 개요
│   ├── dashboard.md                  # 관리자 대시보드 (그룹별 사용량)
│   ├── user-management.md            # 사용자 만들기 · 고치기 · 지우기, 역할
│   ├── group-management.md           # 그룹과 자원 한도
│   ├── registry-management.md        # 사내 이미지 저장소 등록
│   ├── cluster.md                    # 클러스터 — 상태 · 분포 · 사용량 · 모니터링 · 스토리지
│   └── audit-logs.md                 # 감사 로그
│
├── settings/
│   └── index.md                      # 내 프로필, 비밀번호 (SSH Key는 v1.1에서 일시 비활성)
│
├── troubleshooting/
│   └── index.md                      # 자주 겪는 문제와 해결
│
├── release-notes/
│   ├── index.md                      # 날짜순 목차
│   └── 2026-05-29.md                 # v1.1.0 — 표준 포트, Pod 진단, 보안 격리, 인스턴스 카탈로그
│
├── retype.yml                        # Retype 사이트 설정
└── .github/workflows/retype.yml      # GitHub Pages 자동 배포
```

## 🛠 로컬 미리보기

```bash
# Retype CLI 설치 (Node.js 필요)
npm install -g retypeapp

# 로컬 서버 띄우기
retype watch
```

## 📝 문서를 고치실 분께

- 컨테이너 / 스토리지 / 이미지 / 감사 로그 사용 흐름이 바뀔 때마다 해당 페이지를 함께 고칩니다.
- 새 회차가 나오면 `release-notes/YYYY-MM-DD.md` 형태의 파일을 새로 만들고 `release-notes/index.md` 표에 한 줄을 더합니다.
- 화면 캡처는 `static/` 에 둡니다.
- **용어는 한 곳에서만 정의**합니다. Cluma 고유 용어가 새로 생기면 `getting-started/concepts.md` 의 정의를 먼저 손보고, 다른 페이지에서는 그 페이지를 링크합니다.
- 외부에 공개되는 문서이므로 가능한 한 쉬운 표현을 씁니다. 어쩔 수 없이 기술 용어가 등장한다면 짧게 풀어 적거나 `concepts.md` 의 정의로 링크합니다.
