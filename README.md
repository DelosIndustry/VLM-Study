# Vision Language Models Study

<div align="center">
  <a href="https://learning.oreilly.com/library/view/bijeon-eoneo-model/0642572302856/">
    <img src="https://vlmbook.com/cover.jpg" width="300" alt="Vision Language Models: Building VLMs with Hugging Face 표지">
  </a>
  <br><br>
  <strong>『비전 언어 모델: Building VLMs with Hugging Face』를 따라가는 실습 저장소</strong>
  <br>
  이론을 코드로 확인하고, 실험 과정과 결과를 장별 Jupyter Notebook으로 기록합니다.
</div>

## 소개

이 저장소는 Merve Noyan, Miquel Farré, Andrés Marafioti, Orr Zohar가 쓴
[『비전 언어 모델』 한국어판](https://learning.oreilly.com/library/view/bijeon-eoneo-model/0642572302856/)을
학습하며 직접 작성한 코드와 노트를 모아 두는 공간입니다.

책의 흐름에 맞춰 VLM의 기초부터 데이터 전처리, 학습과 미세 조정, 추론 최적화,
문서·영상 이해, Any-to-Any 모델과 에이전트형 VLM까지 차근차근 실습하는 것을 목표로 합니다.

## 학습 내용

| 장 | 주제 | 상태 |
| --- | --- | :---: |
| 1 | 시각과 언어의 소개 | 🧪 실습 중 |
| 2 | 시각 언어 모델의 응용 | ⏳ 예정 |
| 3 | 비전 언어 모델 훈련 | ⏳ 예정 |
| 4 | VLM을 위한 훈련 데이터 및 전처리 | ⏳ 예정 |
| 5 | 훈련 후 비전 언어 모델 | ⏳ 예정 |
| 6 | 비전 언어 모델의 핵심 아키텍처 | ⏳ 예정 |
| 7 | 대규모 추론을 위한 모델 배포 | ⏳ 예정 |
| 8 | 문서 AI | ⏳ 예정 |
| 9 | 영상-언어 모델 | ⏳ 예정 |
| 10 | Any-to-Any 모델 | ⏳ 예정 |
| 11 | 심화 주제 및 최신 연구 | ⏳ 예정 |

## 현재 실습

### Chapter 01 — CLIP 제로샷 이미지 분류

[ch01/main.ipynb](./ch01/main.ipynb)에서는 Hugging Face Transformers와
`openai/clip-vit-large-patch14` 모델을 사용해 이미지와 후보 텍스트 사이의 유사도를 계산합니다.

- `AutoProcessor`와 `AutoModelForZeroShotImageClassification`을 이용한 직접 추론
- 이미지·텍스트 입력 전처리와 로짓의 확률 변환
- `pipeline`을 이용한 간결한 제로샷 이미지 분류

## 저장소 구조

```text
VLM/
├── ch01/
│   └── main.ipynb   # CLIP 제로샷 이미지 분류
└── README.md
```

새로운 실습은 `ch02`, `ch03`과 같이 장별 디렉터리에 추가할 예정입니다.

## 실행 환경

- Python 3.10+
- JupyterLab 또는 Jupyter Notebook
- PyTorch
- Hugging Face Transformers
- Pillow, Requests
- CUDA를 지원하는 NVIDIA GPU 권장

현재 노트북은 CUDA 장치(`cuda`, `device=0`)를 사용합니다. GPU 없이 실행하려면
모델과 입력의 장치를 `cpu`로 변경하고 pipeline의 `device` 설정도 함께 조정해야 합니다.

## 시작하기

```bash
git clone https://github.com/DelosIndustry/VLM-Study.git
cd VLM-Study

python -m venv .venv
source .venv/bin/activate

python -m pip install --upgrade pip
pip install jupyterlab pillow requests torch transformers

jupyter lab
```

JupyterLab이 열리면 원하는 장의 `main.ipynb`를 선택해 셀을 순서대로 실행합니다.
첫 실행 시 Hugging Face Hub에서 모델 가중치를 내려받으므로 인터넷 연결과 충분한 저장 공간이 필요합니다.

## 참고 자료

- [『비전 언어 모델』 한국어판 — O'Reilly Learning](https://learning.oreilly.com/library/view/bijeon-eoneo-model/0642572302856/)
- [Vision-Language Models 공식 웹사이트](https://vlmbook.com/)
- [공식 코드 및 노트북 — Hugging Face](https://huggingface.co/vlmbook)
- [Hugging Face Transformers 문서](https://huggingface.co/docs/transformers/)

## 안내

이 저장소는 개인 학습을 위한 비공식 실습 기록이며 O'Reilly 또는 저자진의 공식 저장소가 아닙니다.
도서의 본문, 표지 및 공식 예제에 대한 권리는 각 저작권자에게 있습니다.
