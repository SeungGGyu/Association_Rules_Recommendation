# Association Rule을 활용한 세트 메뉴 추천 프로젝트

### 사용언어
python, R

## 1. 배경 및 필요성
현대 사회에서는 선택의 폭이 넓어짐에 따라 소비자들이 선택을 하기 어려워하는 '선택의 역설' 현상이 발생하고 있다.
이러한 문제를 해결하기 위해, 소비자가 만족할 수 있는 세트 메뉴를 추천함으로써 선택의 폭을 좁히고자 한다.

## 2. 분석 목적
본 프로젝트의 목적은 배달 음식 주문 시 소비자의 만족도를 높이기 위한 메뉴 조합을 추천하는 것이다.
연관규칙 분석을 통해 소비자들이 함께 주문하는 패턴을 분석하고, 이를 기반으로 세트 메뉴를 제안하여 소비자 만족도를 향상시키는 전략을 마련한다.

## 3. 사용 데이터 및 획득 방법
요기요에서 수집한 '사용자' 리뷰 데이터를 사용했다. 이 데이터는 크롤링을 통해 획득하였으며, 각리브에서 주문된 메뉴들을 추출하고 정제한 후 분석에 활용하였다.
또한, 메뉴명을 정리하고 통일시키는 전처리 과정을 거쳤다.

## 4. 분석 과정
### 4.1 데이터 전처리
주어진 리뷰 데이터를 정제하여 메뉴명을 추출하고, 메뉴 사전을 작성하여 다양한 메뉴 이름을 통일시켰다.
또한, 별점 기준으로 4점 이상의 리뷰만을 선별하여 분석의 대상으로 삼았다.

### 4.2 연관규칙 분석
R을 사용하여 연관규칙 분석을 수행하였다. 최소 지지도와 최소 신뢰도를 설정하여 조건을 만족하는 연관규칙을 발견하고, 이를 통해 소비자들이 자주 함께 주문하는 메뉴 조합을 파악한다. 

### 4.3 세트메뉴 추천 전략
**1) 고정된 세트메뉴 추천: 가장 인기 있는 메뉴 조합을 기준으로 고정된 세트메뉴를 추천한다**

![1](https://github.com/user-attachments/assets/b9766a6f-8475-4e7c-8f2e-c4fca26ed6f7)

**Support = 0.1 / Confidence=0.0 / minlen=2**


![2](https://github.com/user-attachments/assets/c1e868c1-8fb2-4433-a8c5-c11370610863)

**Support = 0.09 / Confidence=0.0 / minlen=2**


![3](https://github.com/user-attachments/assets/534353af-c9e1-4c79-86a2-6c2bb4ea1de4)

**Support = 0.05 / Confidence=0.0 / minlen=2**



**2) 개별 메뉴 선택 시 추천: 특정 메뉴를 선택했을 때 자주 함께 주문되는 메뉴를 추천합니다. 이 경우에는 신뢰도가 높은 조합을 우선적으로 제안한다.**

3) ![4](https://github.com/user-attachments/assets/8a04fbab-6527-4106-b369-7dc199371744)
   
**Support = 0.001 / Confidence=0.5 / minlen=2**
