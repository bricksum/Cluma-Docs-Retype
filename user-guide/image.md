---
label: 이미지
icon: image
order: 80
---

# 이미지

커스텀 이미지 등록 및 레지스트리 탐색 방법을 설명합니다.

---
 
## 이미지 유형
 
Cluma에서 컨테이너 생성 시 사용할 수 있는 이미지는 세 가지입니다.
 
| 유형 | 설명 |
|------|------|
| Registry 이미지 | 관리자가 등록한 Private Registry에서 탐색하여 선택합니다. |
| 퍼블릭 이미지 | Docker Hub 등 퍼블릭 Registry의 이미지 주소를 직접 입력합니다. |
| 커스텀 이미지 | 사용자가 직접 등록한 이미지입니다. |
 
---
 
## Registry 이미지 탐색
 
컨테이너 생성 1단계에서 Registry를 선택하면 등록된 이미지 목록을 탐색할 수 있습니다.
 
1. 이미지 선택 화면에서 Registry를 선택합니다.
2. 이미지 이름으로 검색하거나 목록에서 선택합니다.
3. 태그를 선택합니다.
 
---
 
## 퍼블릭 이미지 직접 입력
 
Registry에 등록되지 않은 퍼블릭 이미지는 주소를 직접 입력하여 사용할 수 있습니다.
 
```
# 예시
pytorch/pytorch:2.1.0-cuda11.8-cudnn8-runtime
nvcr.io/nvidia/tensorflow:23.10-tf2-py3
```
 
클러스터에서 외부 네트워크 접근이 가능한 경우에만 사용할 수 있습니다. 외부 접근이 제한된 환경에서는 관리자에게 문의합니다.
 
---
 
## 커스텀 이미지 등록
 
자체 빌드한 이미지를 Cluma에 등록하여 컨테이너 생성 시 재사용할 수 있습니다.
 
1. 사이드바에서 **이미지**를 선택합니다.
2. **이미지 등록** 버튼을 클릭합니다.
3. 아래 항목을 입력합니다.
 
| 항목 | 설명 |
|------|------|
| 이름 | 이미지 표시 이름 |
| 이미지 주소 | Registry URL 포함 전체 이미지 경로 |
| 태그 | 이미지 태그 (예: latest, v1.0) |
 
등록한 이미지는 컨테이너 생성 시 커스텀 이미지 목록에서 선택할 수 있습니다.
 
---
 
## 권장 이미지
 
AI / ML 워크로드에 일반적으로 사용되는 기본 이미지 예시입니다.
 
| 용도 | 이미지 |
|------|--------|
| PyTorch (CUDA 11.8) | `pytorch/pytorch:2.1.0-cuda11.8-cudnn8-runtime` |
| TensorFlow (CUDA 12) | `nvcr.io/nvidia/tensorflow:23.10-tf2-py3` |
| JupyterLab | `jupyter/scipy-notebook:latest` |
| Ubuntu + CUDA | `nvidia/cuda:12.2.0-devel-ubuntu22.04` |
 
---
 
## 다음 단계

- [컨테이너 관리](./container.md)
- [스토리지 관리](./storage.md)
 