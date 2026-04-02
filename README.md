# Cluma Docs

> Cluma GPU 클러스터 관리 플랫폼 공식 기술 문서

## 🔗 문서 사이트

**[https://bricksum.github.io/Cluma-Docs-Retype](https://bricksum.github.io/Cluma-Docs-Retype)**

## 📋 문서 구조

```
CLUMA-DOCS-RETYPE/
├── index.md                          # 홈 (Cluma 소개 + 문서 전체 안내)
│
├── getting-started/
│   ├── index.md                      # 설치 개요 및 빠른 시작 가이드
│   └── prerequisites.md              # 사전 요구사항 (K8s 버전, StorageClass, GPU 드라이버 등)
│
├── concepts/
│   └── index.md                      # 핵심 개념 (유저/관리자/그룹/컨테이너/스토리지)
│
├── user-guide/
│   ├── index.md                      # 사용자 가이드 개요
│   ├── container.md                  # 컨테이너 생성 6단계 + SSH/Jupyter/VSCode 접속 방법
│   ├── storage.md                    # 스토리지 생성/마운트/공유 방법
│   ├── image.md                      # 커스텀 이미지 등록 및 레지스트리 탐색
│   └── monitoring.md                 # 개인 대시보드 (CPU/GPU/메모리/스토리지 현황)
│
├── admin-guide/
│   ├── index.md                      # 관리자 가이드 개요
│   ├── user-management.md            # 유저 생성/수정/삭제, 그룹 할당, 리소스 한도 설정
│   ├── node-management.md            # 클러스터 노드 등록/수정/활성화, GPU 모델/MIG 설정
│   └── registry-management.md       # 컨테이너 이미지 레지스트리 등록 및 관리
│
└── troubleshooting/
    └── index.md                      # 자주 발생하는 오류 및 해결 방법 (Pending, GPU 미인식 등)
```
