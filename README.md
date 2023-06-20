![image](https://user-images.githubusercontent.com/79899779/235826504-b0711728-fa28-4871-9190-2dca7b8f8218.png)


<h3 align="center"><b>🛠 Tech Stack 🛠</b></h3>
</br>
<p align="center">

<img src="https://img.shields.io/badge/tensorflow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white"/>
<img src="https://img.shields.io/badge/matplotlib-3776AB?style=flat-square&logo=matplotlib&logoColor=white"/>
<img src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/numpy-013243?style=flat-square&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/torch-EE4C2C?style=flat-square&logo=torch&logoColor=white"/>
<img src="https://img.shields.io/badge/transformers-409FFF?style=flat-square&logo=transformers&logoColor=white"/>
<img src="https://img.shields.io/badge/scikit-learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white"/>
</div>

#  🎮Mobile Bert를 활용한 메타크리틱 게임 리뷰 분석🎮





# 1.개요

## 문제정의
● 평소에 스팀게임을 즐겨한다. 그러다 문득 사람들이 게임에 리뷰를 다는 것에 흥미를 느꼇고, 메타크리틱이란 사이트를 알았다. 게임리뷰가 게이머들에게
 어떤 영향을 끼치는지 알고 싶었고 데이터를 추출한 다음 가공해 긍부정으로 나누어 분석을 하여서 데이터 모델로 나타내고 싶었다.



## 1-1 메타크리틱이란?

 
 ![image](https://user-images.githubusercontent.com/79899779/235685202-01c8b30b-60b5-4939-8750-f2595cc4320c.png)




 
 ## 메타크리틱은 Meta critic이란 이름에서 알 수 있듯이 비평가와 유저들의 의견을 종합하는 사이트이다.
 - CBS Interactive 산하 사이트로 CNET, GAMESPOT이 자매 사이트이다.

- 특정한 하나의 미디어에 국한되지 않고 다양한 종류의 미디어를 다루는데 그중  게임 부분에 있어서 큰 영향력을 발휘하는 곳이다.

- 리뷰뿐만 아니라 리뷰의 평균 점수를 종합한다.


이번 프로젝트에서는 메타크리틱 리뷰들을 이용해 긍부정 예측을 통한 인공지능 모델을 개발할 것이다.  
리뷰가 소비자들에게 주는 영향력과 그에 따른 게임 산업에 관해 다룬다.




## 리뷰에 따른 점수 분포도
![image](https://user-images.githubusercontent.com/79899779/235728670-651931c5-3f74-4af6-a505-b280ce5b92b7.png)

보통 90점 전후는 명작으로 부르며 메타크리틱 측에서도 평론가 리뷰 15개 이상 조건으로 90점 이상의 게임들은 'MUST-PLAY' 배지가 주어진다.  게임 한정으로 75 이상은 초록색 호평, 50 내지 60대는 노란색 보통, 그 미만을 좋은 평 준 평론가들보다 안 좋은 평 준 평론가들이 더 많은 빨간색으로 분류된다. 인디 게임의 경우 그래픽 때문에 저평가되는 경향이 있어 80점 이상이면 상당한 명작이라고 보면 된다.


![image](https://user-images.githubusercontent.com/79899779/235729050-301b9169-851d-45cf-8dd9-5836ec7ac28a.png)
#### 자격을 얻은 게임에 주어지는 엠블럼





#### 츨처:https://www.metacritic.com/ 
#### 출처:https://namu.wiki/w/%EB%A9%94%ED%83%80%ED%81%AC%EB%A6%AC%ED%8B%B1


## 1-2 게임 리뷰가 가지는 영향력
### 리뷰를 통한 게임 판매량 영향 
● 오늘날 온라인을 통해 생성되는 구전은 소비자들에게 지대한 영향을 미치고 있다.  이후 머신러닝 기법을 적용한 감성 분석을 시행하여 리뷰의 감성을 분류하고, 이를 분석에 적용하였다. 메티크리틱 리뷰는 텍스트로 구성되어 있어 기존 온라인 리뷰의 영향력을 검증한 문헌에서 주로 사용하고 있는 리뷰 평점과는 다른 접근 방식이 요구된다. 이에 리뷰를 분석 가능한 형식으로 가공하기 위하여 베이지안 분류 방식을 적용한 뒤, 리뷰가 긍정적인지 부정적인지를 확인하여 변수로 활용하였다.
연구 결과 메타크리틱 리뷰의 수는 판매량에 긍정적인 영향을 미치는 것으로 나타났다. 이는 게임의 리뷰가 많아질수록 소비자들의 게임 선택에 정의 영향을 미친다는 것을 뜻한다.

### 리뷰를 통한 게임산업 매출 영향력
● 또한 메타크리틱 리뷰가 긍정적일수록 비디오 게임의 성과에도 정의 영향을 미치는 것을 확인하였다. 더불어 이번 프로젝트에서  엔트로피 개념을 활용하여 온라인 리뷰 감성의 분포에 따라 온라인 리뷰의 효과가 조절됨을 확인하였다. 엔트로피가 높아 소비자 리뷰의 의견이 갈릴 경우 메타크리틱 리뷰의 양과 극성의 효과는 모두 감소하였으며, 이는 온라인 구전의 분포가 리뷰가 미치는 영향을 조절할 수 있음을 시사한다. 본 프로젝트 는 게임 산업에서의 온라인 리뷰의 영향력을 알아봄으로써 현재 온라인 매체에서의 소비자들의 활동이 어떻게 실제 산업과 매출에 영향을 주고 있는지를 확인하였다는 점에서 의의를 지닌다.



# 2.데이터소개
## 2-1 데이터 구성
● 출처:https://www.kaggle.com/datasets/skateddu/metacritic-critic-games-reviews-20112019
 |review|game |score|label|permute|
|---|---|---|---|
|리뷰|게임이름|점수|라벨|교환









## 2-3 라벨 분포 및 구성

● 2011년 부터 2019년 까지 총 125876개의 리뷰, 3910개의 게임 0.0~100.0점 까지의 점수  
● 출처:https://www.kaggle.com/datasets/skateddu/metacritic-critic-games-reviews-20112019
## 1.데이터 불러오기
|Index|Review|Score|Date|Game|
|---|---|---|---|---|
|1|Metro: Last Light is a clear improvement from its predecessor and offers a very atmospheric shooting experience that borders on the survival horror genre.	|89	|1/22/2022	All I |Metro: Last Light|
|2|Night in the Woods is an universal game about the fear of becoming and adult. A fear to struggle with politics, money and family. A fear to lose your beloved ones and yourself. A fear to life itself. But it's also a survival guide to life and adulthood and one of the best written videogames of the last few months.	|70|	6/26/2022|Little nightmare	|
|3|The stages are generous in size and some of them are true level design gems, accompanied by a decidedly inspired soundtrack.	|60|	8/7/2021	|Portal|
|4|A perfect game for My Hero Academia's fans, the game is a fun beat'em up, but repetitive, not for players that don't love the manga/anime.	|90|	7/28/2016|Alan wake|






## 2.결측치

![image](https://user-images.githubusercontent.com/79899779/235826289-4f37d5bf-5a26-49ce-9a31-695e323eff20.png)



## 3.데이터 시각화(라벨,분포,데이터 구성)
![image](https://user-images.githubusercontent.com/79899779/235826051-6abf0176-f8a6-437b-a4ea-ecdfba69d1ec.png)
 
 
 ● Jupiter로 데이터를 전체적으로 표현 했을 떄  긍정(Postive):89점~75점 사이와 긍정(Postive):74점~50점 사이가
 보통 분포적이다. 

![image](https://github.com/okj2670/sentiment_analysis/assets/79899779/68bdcb2a-3a03-42a0-8391-54b69bd5329f)
 
● 데이터를 추출해 파이 그림으로 표현해 보면 88%의 긍정과 12%의 부정으로 나타 낼수 있었다.
 
#### ● - 긍정(Postive):100점~90점  
#### ● - 긍정(Postive):89점~75점  
#### ● - 부정(Negative):49점~20점 
#### ● - 부정(Negative):19점~0점 

![image](https://user-images.githubusercontent.com/79899779/235826171-9df94023-c63e-4a0a-9206-9b8a110bd2e0.png)
● Review:125876개의 리뷰 데이터













# 3. 결론
2011년 부터 2019년 까지 메타크리틱 스코어를 보면서 소비자가 대부분 게임리뷰에 신경 쓰면서 게임에 대한 평가가 높을수록
소비가 증가하였다. 반대로 혹평을 받은 소수의 게임은 외면 받거나 판매량이 적다. 리뷰는 소비자들에게 중대한 영향을 끼친다.










