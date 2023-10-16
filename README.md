# 한국 수어 지문자 자판 시스템 

<br>

한국의 등록 청각 장애인 수는 2021 년 기준 411,749 명에 달하며, 이는 전체 등록 장애인의 약 15%에 해당하는 수치로 지체 장애인(45%) 다음으로 가장 높은 비율이다.
문화체육관광부 ‘2020 년 한국수어 활용 조사’에 따르면, 필담은 청인과 농인이 소통하는 때 쓰이는 가장 흔한 방법이다. 하지만 조사 응답자의 26.1%는 필담을 전혀 또는 거의 이해하지 못하는 것으로 보인다.

본 프로젝트에서는 청각장애인의 보다 편리한 의사소통 을 위해 한국 지문자(finger-spelling) 수어 자판 시스템 을 제안한다. 
본 시스템은 먼저 MediaPipe로 영상에 서 손과 손가락의 랜드마크를 추출한다. 그 후 추출된 랜드마크의 좌표를 특성으로 하여 XGBoost로 한글 을 표현하는 지문자를 인식한다. 인식된 한글은 PyAutoGUI를 통해 사용자가 원하는 입력창에 입력된다. 자판 시스템에 사용된 모델은 머신러닝을 통해 학습한 모델로, 딥러닝 모델을 사용한 시스템에 비해 가볍고 높은 인식률을 가지고 있다.

<br>
<br>

### 데이터의 구성

본 시스템에서 인식할 수어 지문자 데이터는 자음 18 개(ᄀ,ᄁ,ᄂ,ᄃ,ᄄ,ᄅ,ᄆ,ᄇ,ᄈ,ᄉ,ᄋ,ᄌ,ᄍ,ᄎ,ᄏ,ᄐ,ᄑ,ᄒ), 모음 17 개(ᅡ,ᅣ,ᅥ,ᅧ,ᅩ,ᅭ,ᅮ,ᅲ,ᅳ,ᅵ,ᅢ,ᅤ,ᅦ,ᅨ,ᅬ,ᅱ,ᅴ), 숫자 10 개(0~9)이다. 웹캠을 통해 직접 수집하였으며 하나의 문자 당 10개의 영상 수집, 100배 증강을 통해 총 4500개가 학습 데이터로 사용되었다.

<br>
<br>

### 성능평가 
LSTM은 98.9%, XGBoost는 99.9%로 두 모델 모두 준수한 정확도를 보인다.
  각 모델의 정확도와 더불어, LSTM과 XGBoost 모델의 안정성을 측정하여 비교하였다.
 안정성 측정은 9개 단어들을 모델에 인식시킨 후, 각 음절을 정확하 게 맞춘 것으로 계산되었다. 실험 결과, LSTM은 45.83%, XGBoost는 79.17%의 안정성을 보여줬다. XGBoost가 더 높은 안정성을 가지고 있음을 알 수 있다. 정확도, 안정성 결과와 더불어 모델의 사용 범용성을 늘리기 위해 머신러닝 모델인 XGBoost를 최종 모델로 선정하였다.

<br>
<br>

### 개발 환경
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=TensorFlow&logoColor=white"/> <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=Keras&logoColor=white"/> <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=OpenCV&logoColor=white"/>
<!-- plastic, flat, flat-square, for-the-badge, social -->

<br>
<br>

### 실행방법

1. cmd에서 `pip install -r requirements.txt`로 필요 라이브러리 설치한다.
2. 타이핑 하고 싶은 부분에 커서를 놓는다.
3. `main.py`을 실행하고 웹캠을 보며 오른손으로 수어를 진행한다.

<br>
<br>

### 조작 방법

숫자 `1`과 `ㅏ`, `2`와 `ㅑ`는 지문자가 똑같기 때문에, 수어로 타이핑을 할 때 숫자와 문자 구분을 해줘야 한다. 

- 왼손 검지 끝을 오른쪽 아래 빨간 블록으로 가져다 대면, 숫자를 입력한다.
- 오른쪽 아래 초록색 블록으로 가저다 대면, 글자를 입력한다.
- 글자를 지우고 싶으면, 왼손 검지 끝을 왼쪽 위 파란 DEL버튼에 위치시킨다. 

<br>
<br>

### 구성도


- 수어 인식 구성도
<img width="600" alt="스크린샷 2023-05-09 오후 7 00 34" src="https://user-images.githubusercontent.com/120548753/237063175-1ee37ccd-6739-440f-afd1-13f113d25d10.png">


- 데이터 처리 구성도
<img width="600" alt="스크린샷 2023-04-17 오후 3 05 23" src="https://user-images.githubusercontent.com/120548753/233043114-b95615d8-4b30-49e5-81e3-db6516f49c9b.png">

<br>
<br>


### 개발 노션 페이지
- [Notion 링크](https://rammm.notion.site/8cbcbdcc3df34477888c92ed92233b13)

