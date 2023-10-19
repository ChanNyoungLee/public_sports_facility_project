<h2 align="center"> 
  <br> 
  공공데이터를 활용한 도시 내 공공체육시설 위치
추천 프로젝트
</h2>
<h3 align="center">
</h3>  
<p align="right">
  <br>이찬녕 외 7명</br>
</p>  

### Abstract
&nbsp;&nbsp;다양한 이동 수단의 사용과 업무, 교육, 오락을
위한 컴퓨터 사용이 증가함에 따라 현대인의 운동량
이 현격하게 줄어들고 있는 바, 심혈관 질환, 당뇨병
등 성인병 환자와 비만 인구가 증가하는 실정이다.
이러한 질병들은 규칙적인 신체활동을 통해 예방할
수 있는데, 국가와 지역사회는 국민의 신체활동을
격려하고 촉진하는 방법 및 관련 시설을 추가하고
장려하는 움직임을 보이고 있다.
<br>
&nbsp;&nbsp;이에 발맞추어, 최근에는 증가하는 국민 소득에
따라 규칙적인 체육활동 참여도가 높아지고 있다.
연구에 따르면, 거리상 가까운 곳에 위치하고 저렴
하게 이용할 수 있는 공공체육시설의 선호도와 이용
률이 가장 높다.[1] 여기서 공공체육시설이란 국가나
지방 자치단체 또는 공공단체가 국민의 체육활동에
제공하기 위하여 설치 및 관리, 운영하는 체육시설
을 말한다.[2]
<br>
&nbsp;&nbsp;체육시설의 수요 증가에 따라 공공스포츠시설의
보급률은 개선되었지만, 선진국 수준에는 여전히 미
치지 못하고 있다. 인구밀도가 높은 도시지역에서도
접근성은 확보되나 서비스 반경 내 거주 인구가 많
아 적정 서비스가 이루어지지 못하는 경우가 다수
발생하므로 추가적인 시설 공급이 필요하다.[3] 이에
따라, 본 연구는 공공빅데이터를 활용, 서울시 내 공
공체육시설 확충이 필요한 지역을 분석하고, 군집
분석을 통해 서울시 자치구별 공공체육시설의 입지
선정 예측에 대해 논하고자 한다.

### Method
#### 1. 사용 모델
<br>
<b>다중회귀분석</b>
<br>
&nbsp;&nbsp;다중회귀분석은 2개 이상 복수의
독립변수들을 이용한 회귀분석으로, 독립변수가 종
속변수에 미치는 영향력의 크기를 파악하고 이를 통
하여 독립변수의 일정한 값에 대응하는 종속변수 값
을 예측하는 모형을 산출하는 방법이다.
<br>
[4] 수식은
아래와 같다.
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%801.png" width="300"/>
</p>
<p align="center">
</p> 
<br>
&nbsp;&nbsp;여기서 y는 종속변수, 각 β는 k번째 회귀계수, 각 x는 k
번째 독립변수를 의미한다. 여기서는 선행연구[5]의
공공서비스 입지요인 지표들을 독립변수로 사용했
으며, 공공체육시설의 수를 종속변수로 하였다.
<br>
<b>k-means clustering</b>
<br>
&nbsp;&nbsp;k-means clustering[6]은 중
심점과 각 개체 간의 유클리디안 거리를 계산해 가
까운 군집으로 개체를 분류하는 군집화 비지도 학습
알고리즘이다. 개체를 각 군집으로 분류한 후 평균
값으로 중심점을 갱신하며, 더이상 갱신이 되지 않
을 때까지 알고리즘을 반복한다. 유클리디안 거리
계산식은 아래와 같다.
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%802.png" width="300"/>
</p>
 <br>
&nbsp;&nbsp;군집의 개수는 하이퍼 파라미터로 사용자가 제시
하나, 보통은 elbow 방법와 silhouette 방법을 활용
하여 추정한다. 여기서는 elbow 방법을 활용하였는
데, 이것은 군집 수에 대한 SSW(Sum of Squares
Within the clusters)의 플롯(plot)으로부터 최적 군
집 개수를 추정한다.
<br>
<br>
#### 2. 입지 요인 도출 및 추가 설치 입지 추정
<br>
&nbsp;&nbsp;클러스터링을 위한 입지요인 선택을 위해 다중회
귀분석을 진행하였다. 독립변수 간 다중공선성 제거
를 위해 상관계수의 크기가 0.7 이상인 변수를 제거
하였다. 나머지 변수를 사용해 backward stepwise
회귀분석을 적용한 결과는 Table 1과 같다.
<br>
&nbsp;&nbsp;backward stepwise 다중회귀분석 결과 인구수, 재산
세, 수급인구비율을 입지요인으로 선정하였다.
<br>
&nbsp;&nbsp;서울시 수요 불충족 지역구 K-means clustering
결과를 지도 시각화한 결과는 Fig.1과 같다.
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%803.png" width="600"/>
</p>
<p align="center">
<I>Table 1. backward stepwise 다중회귀분석 결과</I>
</p>
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%804.png" width="400"/>
</p>
<p align="center">
<I>Fig 1. 서울시 k-means clustering 결과</I>
</p>
<br>
<br>

#### 3. 공공체육시설 추가 설치 입지 예측
<br>
&nbsp;&nbsp;공공체육시설의 최종 입지 예측을 위해 클러스터별
인구 만 명당 체육시설 수의 비율을 구했다. 수식은
아래와 같다.
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%805.png" width="300"/>
</p>
<br>
&nbsp;&nbsp;여기서 x는 추가 설치 개수를 말한다.
<br>
&nbsp;&nbsp;이 비율이 동일하도록 각 cluster에 추가로 필요한
체육시설 개수를 결정하였다. 실제로는 비율이 완벽
하게 동일하도록 개수 선정이 불가능한 바, 여기서
각 cluster 비율의 오차제곱합이 가장 작아지도록 하
는 값을 선정하였다.<br>
&nbsp;&nbsp;이후, 각 cluster의 중심점을 구해 그 중심점으로
부터 가까운 동부터 시설을 하나씩 설치하는 방향으
로 위치를 선정했다. 선정된 추가 설치 입지는 Fig.
2와 같다.
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%806.png" width="600"/>
</p>

<p align="center">
 <I> Fig 2. 서울시 공공체육시설 추가 설치 입지</I>
</p>
<br>
<br>

### Result
<br>
&nbsp;&nbsp;본 연구의 목적은 지역 주민들의 접근성과 기대
수요를 파악하여 적절한 입지 위치를 제안하는 위치
선정모델을 만드는 것이다. 먼저 자료 수집이 용이
한 서울시 내에서 자치구별 공공체육시설 수를 확인
하고 서비스 지역 적정 개소수를 기준으로[7] 공공
체육시설의 확충이 필요한 지역을 선별하여
clustering 하였다.
<br>
&nbsp;&nbsp;기존 공공체육시설 현황과 선행연구의 입지분석
지표를 활용한 회귀분석을 통해 인구수, 재산세, 수
급인구 비율을 입지요인으로 도출하였다. 다음으로
서울시 내 수요 불충족 지역구를 대상으로 k-means
clustering 분석을 진행하였다. 앞에서 도출한 입지
요인을 변수로 cluster를 나누고 행정동을 배분하여
cluster 별 만 명당 공공체육시설 설치 비율이 같아
지도록 공공체육시설 설치 개수를 결정한 뒤 각
cluster의 중심점으로부터 가까운 동 순으로 공공체
육시설의 추가 설치가 필요한 동을 선정, 시각화하
였다.
<br>
&nbsp;&nbsp;본 모델을 적용하여 공공체육시설 추가 설치에 대
해 예측했을 때 Fig. 3에서 볼 수 있듯이, 공공체육
시설이 더 균등하게 배분되어 있음을 알 수 있다.
공공체육시설의 균등하게 배분된 정도를 분산으로
정량화하면, 이전 (Fig. 3-가)는 0.0083, 추가 설치
경우 (Fig. 3-나)는 0.0040으로, 추가 설치 시 각 자
치구 별 편차가 더 줄었음이 확인되었다. 이는 더
많은 자치구에서 더 균등한 조건으로 체육시설을 이
용할 수 있음을 의미하며, 결국 전 국민 신체 건강
증진 가능성을 높이는 계기가 될 수 있다.
<br>
<br>
<p align="center">
  <img src="https://github.com/ChanNyoungLee/public_sports_facility_project/blob/master/%EC%9D%B4%EB%AF%B8%EC%A7%80/%EC%9D%B4%EB%AF%B8%EC%A7%807.png" width="500"/>
</p>
<p align="center">
  <I>Fig 2. 서울시 공공체육시설 추가 설치 입지</I>
</p>
&nbsp;&nbsp;최근 국민 건강이 중요한 이슈로 부상함에 따라
체육활동의 수요가 늘어나면서 공공체육시설 증설의
필요성이 높아졌다. WHO에 따르면[8], 신체활동은
심혈관 질환, 암, 당뇨 등 비전염성 질환 예방에 기
여한다. 실제로 연구 과정에서 비교해본 결과, 공공
체육시설 필요 개수가 충족된 자치구의 당뇨, 고혈
압, 비만율이 그렇지 않은 자치구에 비해 눈에 띄게
우세함을 보였다 (p < 0.05). 본 모델을 통해 체육시
설이 적절한 위치에 균등하게 배분됨에 따라 더 많
은 사람의 신체활동 증진을 기대할 수 있으며, 이를
통해 국민 건강 수준 향상 및 의료비 감소 등 사회
적 파급 효과를 불러일으킬 것으로 기대한다.
<br>
<br>
### Reference
1] 국민생활체육 참여실태 조사, 문화체육관광
부,75-77 ,2021
<br>
[2] 이태신, 체육학대사전, 민중서관, 2000
<br>
[3] 생활 SOC 추진단, 생활SOC 3개년 계획(안), 국
무조정실,9 , 2019
<br>
[4] 이선희, 윤동현, 고준환, 다중회귀분석을 이용한
서울시 1인 가구의 연령별 분포요인에 관한 연구,
Spatial Information Research, 통권, 84호, 11-21,
2015
<br>
[5] 김헌민, 김희영, 도시 공공서비스 시설의 공급
결정요인, 사회과학연구논총, 제 12권, 109-128, 2004
<br>
[6] 신지은, “RHadoop 플랫폼을 이용한 빅데이터
K-평균 클러스터링.”, 국내석사학위논문, 경상대학교
대학원 ,10 , 2016
<br>
[7] 체육진흥과, 생활밀착형 국민체육센터 모델개발
및 추진 방안 연구, 문화체육관광부,1-5 , 2018
<br>
[8] WHO, Physical activity 2020.11.
https://www.who.int/news-room/fact-sheets/detail/
physical-activity
