# ML 입문자용 NLP 리스트(작성중)
- [fast.ai](http://fast.ai/) 같은 조직 덕분에 모호한 기술 배경지식을 가진 사람도 머신러닝 기초를 배우고 자신만의 모델을 훈련시킬 수 있게 되었다.
- 단순히 머신러닝을 학습하는 것이 목적이 아닌, 머신러닝을 활용하여 프로덕트를 만들어보고 싶은 사람에게 유용한 자원은 그리 많지 않다.
- 본 리스트는 ML에 경험이 없는 누구라도 NLP 프로젝트에 뛰어들 수 있는 방법을 제시한다.
- 리스트의 모든 프로젝트는 실제 기업에 판매된 소프트웨어에서 영감을 받아 제작되었다.

## 프로젝트의 특징
- 리스트에 제시된 모든 프로젝트는 다음과 같이 비슷한 아키텍처를 가지고 있다.
  1. 미리 학습된 모델을 구현한다.
  2. 그 모델을 API로 배포한다.
  3. API를 애플리케이션에 연결한다.
 
- 이러한 접근 방식의 장점
  - ML모델을 위해 빌드된 서버를 통함으로써 애플리케이션의 컴퓨팅 부담을 제거할 수 있고, API를 통한 ML 예측이 가능해진다. 
  - Cortex와 같은 오픈소스 투을 활용하여 API 형태의 모델을 배포하는데 필요한 모든 기반 작업을 자동할 수 있다.

- Cortex를 이용한 모델 배포에 필요한 절차
  - 모델로부터의 예측을 제공하는 파이썬 스크립트 작성
  - 배포를 정의하는 환경 설정 파일 작성
  - 코멘드 라인에서 cortex deploy 실행

## 프로젝트 리스트
다음의 프로젝트 리스트를 확인하고 가장 관심가는 주제를 택하여 마이크로서비스를 제작한다.

### Project 1. 자동완성 기능 An autocomplete feature
- 전통적으로 자동완성 기능은 key-value 검색을 활용해왔지만, 머신머닝을 이용한 방식은 한 단계 발전된 방식이다. 단어나 문구의 전역적인 사전을 참조하는 것 대신에 사용자들의 입력을 기반으로 학습되어 가장 가능성 있는 다음 문구를 예측하도록 한다.
- Gmail이 빠른 답장 기능에서 간단한 문구를 제공하는 것이 그 예이다.

- 사용 모델:RoBERTa (Robustly Optimized BERT Pretraining Approach)
  - 페이스북에서 개발된 NLP 모델로, 학습 접근 방식을 살짝 달리하여 구글 BERT의 성능을 개선시켜 구축했다.
  - 사전 학습된 RoBERTa는 PyTorch Hub를 통해 로드되어 내장된 fill_mask() 메서드를 갖게 된다.
  - fill_mask() 메서드에 스트링을 입력하면, RoBERTa가 예측하는 다음 단어나 문구가 있는 위치를 가리키게 된다.
  - 참조된 위치에서 예측된 결과물을 가져온다.
  - 이제 이 RoBERTa를 API로서 배포하고, 구현하고자 하는 프로젝트에 유저의 입력으로 배포된 모델에 질의하는 코드를 작성한다.


### Project 2. 고객지원 봇 Customer support bot

### Project 3. 예측 텍스트 생성기 Predictive Text Generator

### Project 4. 언어 식별기 Language identifier

### Project 5. 미디어 모니터 Media monitor


## Reference
- https://medium.com/@calebkaiser/a-list-of-beginner-friendly-nlp-projects-using-pre-trained-models-dc4768b4bec0
- https://brunch.co.kr/@choseunghyek/7
