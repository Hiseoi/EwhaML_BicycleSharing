# EwhaML_BicycleSharing

## 🚲Bicycle Sharing Demand Prediction
## Project Instruction

위 프로젝트의 목적은 서울시 송파구 따릉이 대여량을 예측하는 것이다.

따릉이 데이터는 [서울 열린데이터광장]([https://data.seoul.go.kr/](https://data.seoul.go.kr/)), 기후 데이터는 [기상자료개방포털]([https://data.kma.go.kr/cmmn/main.do](https://data.kma.go.kr/cmmn/main.do))를 사용하였다. 2021년 4월~2022년 3월까지의 데이터이다.

사용한 모델은 lgbm 이다.


## Data

- [서울시 따릉이대여소 마스터 정보](https://data.seoul.go.kr/dataList/OA-21235/S/1/datasetView.do)
    
    서울시 따릉이대여소에 대한 대여소 ID, 역 주소, 좌표 정보
    
    송파구에 해당하는 대여소 정보 사용
    



- [서울시 공공자전거 이용정보(시간대별)](https://data.seoul.go.kr/dataList/OA-15245/S/1/datasetView.do#)
    
    대여일시, 대여시간, 대여소번호, 대여소명, 정기권유무, 성별, 연령대, 탄소량, 이동거리, 이동시간 정보
    
    송파구에 해당하는 대여소 정보 사용
    



- [서울시 날씨 데이터](https://data.kma.go.kr/cmmn/main.do)
    
    미세먼지농도, 풍속, 습도,적설, 기온, 열지수, 풍향, 증기압, 이슬점온도, 현지기압, 해면기압, 전운량, 등등
    
    송파구에 해당하는 날씨 정보 사용


## Our final data
https://drive.google.com/file/d/1OtzxxUcjfaOVLQrMzTx-cZOpBWYZQhZl/view?usp=share_link



## Code
- 베이스라인
    
    파라미터 없이 기본 모델로 여러 모델의 성능 비교
    
- 정류소별_성능_비교를_통해_Outlier_찾기
    
    잠실동과 방이동에서 모델의 error값이 가장 높은 outlier 정류소 찾기
    
- 대여소별_시간대별_예측
    - 잠실동과 방이동에서 가장 대여량이 높은 정류소를 기준으로 여러 모델 성능 비교, Data preprocessing이 예측 결과에 미치는 영향 비교
    - 잠실동과 방이동의 대여량 Top 4 정류소 대여량 예측
    - 잠실동과 방이동에서 error값이 가장 높은 outlier 정류소의 예측값을 시간대별로 분석해 오류 원인 찾기 

- LGBM_결과_해석
    - 데이터로부터 각 동별 LGBM 성능을 확인하기 위한 전처리 함수와 모델 훈련, 성능 평가 및 피처 중요도 출력 함수 생성 후 다른 모델 성능과 비교
    - 데이터 EDA를 통해 모델 성능에 영향을 줄 요인 선별한 뒤 모델 피처 중요도 및 tree 상의 노드들을 이용해 비교
    - LGBM 하이퍼파라미터 설명


## Contributors

- [김현서](https://github.com/Hiseoi)
- [박보영](https://github.com/bboyeong)
- [이서영](https://github.com/seoyoung-e)
- [정지혜](https://github.com/dahlia52)
- [최하경](https://github.com/FleurHwai)
