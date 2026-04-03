---
label: Prerequisites
icon: checklist
order: 90
---

# 사전 요구사항

Cluma를 설치하기 전에 아래 요구사항을 먼저 확인하세요.

---

## 시스템 요구사항

### Kubernetes 클러스터

| 항목 | 요구사항 |
|------|----------|
| Kubernetes 버전 | 1.29 이상 |
| 클러스터 권한 | 'cluster-admin' |
| 노드 구성 | Control Plane 1대 이상 + Worker Node 1대 이상 |
| GPU 노드 | NVIDIA GPU 탑재 Worker Node (최소 1대) |

### 필수 구성 요소

**StorageClass**

Cluma는 사용자 데이터를 저장하기 위한 StorageClass가 클러스터에 정의되어 있어야 합니다.
NFS 또는 Local 기반의 StorageClass를 권장합니다.

```bash
# StorageClass 확인
kubectl get storageclass
```

**Private Container Registry**

컨테이너 이미지를 관리하기 위한 Private Registry가 필요합니다.
Harbor 또는 클러스터 내부 레지스트리를 사용할 수 있습니다.

```bash
# 레지스트리 접근 확인
docker login <registry-url>
```

**NVIDIA GPU Driver**

GPU 노드에 NVIDIA 드라이버가 설치되어 있어야 합니다.

```bash
# GPU 드라이버 확인
nvidia-smi
```

---

## 필수 도구

로컬 환경에서 Cluma를 설치하고 관리하기 위해 아래 도구가 필요합니다.

| 도구 | 버전 | 용도 |
|------|------|------|
| `kubectl` | 1.29+ | Kubernetes 클러스터 관리 |
| `helm` | 3.0+ | Helm chart 배포 |
| `docker` | 20.0+ | 컨테이너 이미지 빌드 |

### kubectl 설치 확인

```bash
kubectl version --client
```

### helm 설치 확인

```bash
helm version
```

---

## 네트워크 요구사항

- 클러스터 노드 간 내부 통신이 가능해야 합니다.
- Control Plane과 Worker Node 사이에 포트 제한이 없어야 합니다.
- GPU 노드에서 Private Registry에 접근 가능해야 합니다.

---

## 다음 단계

요구사항 확인이 완료되면 [Getting Started](./index.md)로 이동하여 설치를 시작하세요.