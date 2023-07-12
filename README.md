# 한국 수어 지문자 자판 시스템 


## 프로젝트 소개
---
한국의 등록 청각 장애인 수는 2021 년 기준 411,749 명에 달하며, 이는 전체 등록 장애인의 약 15%에 해당하는 수치로 지체 장애인(45%) 다음으로 가장 높은 비율이다.
문화체육관광부 ‘2020 년 한국수어 활용 조사’에 따르면, 필담은 청인과 농인이 소통하는 때 쓰이는 가장 흔한 방법이다. 하지만 조사 응답자의 26.1%는 필담을 전혀 또는 거의 이해하지 못하는 것으로 보인다.

본 프로젝트에서는 청각장애인의 보다 편리한 의사소통 을 위해 한국 지문자(finger-spelling) 수어 자판 시스템 을 제안한다. 
본 시스템은 먼저 MediaPipe로 영상에 서 손과 손가락의 랜드마크를 추출한다. 그 후 추출된 랜드마크의 좌표를 특성으로 하여 XGBoost로 한글 을 표현하는 지문자를 인식한다. 인식된 한글은 PyAutoGUI를 통해 사용자가 원하는 입력창에 입력된다. 자판 시스템에 사용된 모델은 머신러닝을 통해 학습한 모델로, 딥러닝 모델을 사용한 시스템에 비해 가볍고 높은 인식률을 가지고 있다.


## 개발 환경
---
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=TensorFlow&logoColor=white"/> <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=Keras&logoColor=white"/> <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=OpenCV&logoColor=white"/>
<!-- plastic, flat, flat-square, for-the-badge, social -->


## 실행방법
---
1. git clone을 합니다.
2. clone한 폴더로 이동합니다.
3. cmd에서 `pip install -r requirements.txt`로 필요 라이브러리 설치 후 환경 설정을 합니다.
4. `python main.py` 실행 후 타이핑 하고 싶은 부분에 커서를 놓습니다.
5. `main.py`를 실행할 때 나타나는 카메라 피드를 보면서 오른손으로 수어 지문자를 표시하면서 타이핑 진행합니다.

### 조작 방법
❗️ 숫자 `1`과 `ㅏ`, `2`와 `ㅑ`는 지문자가 똑같기 때문에, 수어로 타이핑을 할 때 숫자와 문자 구분을 해줘야 합니다. 
<<<<<<< Updated upstream

6. 왼손 검지 끝을 오른쪽 아래 빨간 블록으로 가져다 대면, 숫자를 입력합니다.
7. 오른쪽 아래 초록색 블록으로 가저다 대면, 글자를 입력합니다.
8. 글지를 지우고 싶으면, 왼손 검지 끝을 왼쪽 위 파란 DEL버튼에 가져갑니다. 
=======
1. 왼손 검지 끝을 오른쪽 아래 빨간 블록으로 가져다 대면, 숫자를 입력합니다.
2. 오른쪽 아래 초록색 블록으로 가저다 대면, 글자를 입력합니다.
3. 글지를 지우고 싶으면, 왼손 검지 끝을 왼쪽 위 파란 DEL버튼에 가져갑니다. 
>>>>>>> Stashed changes


## 구성도
---

- 수어 인식 구성도
<img width="600" alt="스크린샷 2023-05-09 오후 7 00 34" src="https://user-images.githubusercontent.com/120548753/237063175-1ee37ccd-6739-440f-afd1-13f113d25d10.png">


- 데이터 처리 구성도
<img width="600" alt="스크린샷 2023-04-17 오후 3 05 23" src="https://user-images.githubusercontent.com/120548753/233043114-b95615d8-4b30-49e5-81e3-db6516f49c9b.png">




### 개발 노션 페이지
- [Notion 링크](https://rammm.notion.site/8cbcbdcc3df34477888c92ed92233b13)

