# NLP - AI야, 진짜 뉴스를 찾아줘!

* 대회: [2020 NH투자증권 빅데이터 경진대회](https://dacon.io/competitions/official/235658/overview/description/)
* 활동기간: 20/11/23 ~ 20/12/31
* 자세한 내용은 [보고서](https://github.com/SEUNGEUN-1025/NLP-NH/blob/2d49c8c421760b1fdad3583d74f5ee47864fc6d0/%EB%B0%9C%ED%91%9C%EC%9E%90%EB%A3%8C_%EC%96%BC%EA%B7%B8%EB%A0%88%EC%9D%B4.pdf) 를 확인해주세요.

## 📰 분석 문제
- 진짜 뉴스와 가짜 뉴스를 구별하는 빠르고 정확한 알고리즘 개발

## 📰 분석 과정
### 1. 분석 데이터
- 2020.01.01 ~ 2020.06.30까지의 사회, 경제 분야 뉴스 Data
- 기사의 title과 content를 합한 내용을 Input Data로 사용함 
### 2. Tokenizer
- 분석에 필요한 적절한 단어들을 가진 Vocab을 이용한 Tokenizer를 이용해야 함
- 단어 수가 많은 모델([KRBERT(snunlp)](https://github.com/snunlp/KR-BERT))의 tokenizer로 나눈 [단어들](https://github.com/SEUNGEUN-1025/NLP-NH/blob/2d49c8c421760b1fdad3583d74f5ee47864fc6d0/plus%201500%20vocab.csv)의 상위 500개를 추출하여 Tokenizer에 추가
### 3. BERT
- [SKT Brain](https://github.com/SKTBrain/KoBERT)팀이 개발한 KoBERT를 사용하여 분석을 수행함
### 4. Modeling & Training
- KoBERT에 Dense Layer 추가하여 성능을 높이려 함
- 학습 환경

|항목|내용|
|------|---|
|Parameters|92,244,481|
|Batch size|32|
|Training Steps|3340|
|Epochs|13|
|Time|20min/epoch|

## 📰 분석 결과
- Validation Loss = 0.0329 , Validation Accuracy = 0.9936
<img width="1041" alt="loss_acc" src="https://user-images.githubusercontent.com/82666244/116254883-b05c8900-a7ac-11eb-8cb0-0450cdd271c3.png">

- 최종 Test Accuracy = __0.98214__

