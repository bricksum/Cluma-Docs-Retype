---
label: 이미지
icon: image
order: 80
---

# 이미지

커스텀 이미지 등록 및 레포지토리 탐색 방법을 설명합니다.

---

## 이미지 유형

Cluma에서 컨테이너 생성 시 사용할 수 있는 이미지는 세 가지입니다.

| 유형 | 설명 |
|------|------|
| 레포지토리 이미지 | 관리자가 등록한 레포지토리에서 탐색하여 선택 |
| 퍼블릭 이미지 | Docker Hub 등 퍼블릭 이미지 주소를 직접 입력 |
| 커스텀 이미지 | 사용자가 직접 등록한 이미지 |

---

## 레포지토리 이미지 탐색

컨테이너 생성 모달의 Step 2 → 이미지 영역에서 **레지스트리에서 이미지 선택**을 누릅니다.

1. 등록된 레포지토리를 선택합니다.
2. 이미지 이름으로 검색하거나 목록에서 선택합니다.
3. 태그를 선택합니다.

---

## 퍼블릭 이미지 직접 입력

레포지토리에 등록되지 않은 퍼블릭 이미지는 **직접 입력하기** 라디오에서 주소를 직접 입력하여 사용할 수 있습니다.

```
# 예시
pytorch/pytorch:2.1.0-cuda11.8-cudnn8-runtime
nvcr.io/nvidia/tensorflow:23.10-tf2-py3
```

클러스터에서 외부 네트워크 접근이 가능한 경우에만 사용할 수 있습니다. 외부 접근이 제한된 환경에서는 관리자에게 문의합니다.

---

## 커스텀 이미지 등록

자체 빌드한 이미지를 Cluma에 등록하여 컨테이너 생성 시 재사용할 수 있습니다.

1. 사이드바에서 **이미지 목록**을 선택합니다.
2. **이미지 등록** 버튼을 클릭합니다.
3. 아래 항목을 입력합니다.

| 항목 | 설명 |
|------|------|
| 이름 | 이미지 표시 이름 |
| 이미지 주소 | 레포지토리 URL 포함 전체 이미지 경로 |
| 태그 | 이미지 태그 (예: latest, v1.0) |

등록한 이미지는 컨테이너 생성 모달의 **커스텀 이미지** 라디오에서 선택할 수 있습니다.

---

## Base image 요구사항

v1.1부터 컨테이너의 표준 포트(VS Code · SSH · JupyterLab)가 자동으로 노출됩니다. 카드 버튼이 정상 동작하려면 base image 안에서 세 서비스가 실행 가능해야 합니다.

| 서비스 | 컨테이너 내부 포트 | 권장 도구 |
|--------|-------------------|----------|
| VS Code | 8443 | code-server |
| SSH | 22 | OpenSSH (sshd) |
| Jupyter | 8888 | JupyterLab |

자세한 빌드 가이드는 [Base image 가이드](https://github.com/bricksum/cluma/blob/main/docs/container-base-image-420.md)를 참고합니다.

---

## 권장 이미지

AI / ML 워크로드에 일반적으로 사용되는 base image 예시입니다. 표준 포트 서비스가 포함된 이미지를 별도로 빌드하는 것을 권장합니다.

| 용도 | 이미지 |
|------|--------|
| PyTorch (CUDA 11.8) | `pytorch/pytorch:2.1.0-cuda11.8-cudnn8-runtime` |
| TensorFlow (CUDA 12) | `nvcr.io/nvidia/tensorflow:23.10-tf2-py3` |
| JupyterLab (CPU/실험용) | `jupyter/scipy-notebook:latest` |
| Ubuntu + CUDA | `nvidia/cuda:12.2.0-devel-ubuntu22.04` |

!!!note 위 이미지는 표준 포트 서비스를 포함하지 않을 수 있습니다
위 base image에 code-server / OpenSSH / JupyterLab을 추가 설치한 커스텀 이미지를 빌드하는 것을 권장합니다. Cluma 팀이 제공하는 권장 base image가 있다면 관리자에게 문의하세요.
!!!

---

## 다음 단계

- [컨테이너 관리](./container.md)
- [스토리지 관리](./storage.md)
