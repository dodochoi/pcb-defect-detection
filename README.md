# pcb-defect-detection
PCB 데이터를 활용한 불량 및 이상탐지

## Dataset

이 프로젝트는 [DsPCBSD+ (Kaggle)](https://www.kaggle.com/datasets/enisteper1/dataset-of-pcb-surface-defects-dspcbsd?resource=download) 데이터셋을 사용합니다.
용량 및 라이선스 문제로 데이터 자체는 저장소에 포함하지 않습니다.

### 클래스 (9종)
SH, SP, SC, OP, MB, HB, CS, CFO, BMFO

### 사용 방법
1. 위 Kaggle 링크에서 데이터를 다운로드합니다.
2. 압축을 풀어 저장소 루트에 `Data_YOLO/` 폴더로 배치합니다. (`images/train`, `images/val`, `labels/train`, `labels/val` 구조)
3. `data.yaml`의 `path`가 `Data_YOLO`(상대 경로)로 되어 있는지 확인 후 학습을 진행합니다.

## 환경 설정

GPU: NVIDIA RTX 50계열(Blackwell) 기준 CUDA 12.8 빌드 torch 사용.

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

GPU 인식 확인:
```powershell
.\.venv\Scripts\python.exe -c "import torch; print(torch.cuda.is_available(), torch.cuda.get_device_name(0))"
```
