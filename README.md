# 2021_Kangnam_univ._Academic_Seminar
🏆 2021 강남대학교 데이터분석 학술 세미나 우수상 수상 작품<br>
<div align="center">
  <h1>2022 강남대학교 학술제<br><br>
  ⛽ 전기차 급속 충전소 입지 선정</h1>
</div>
<br>
<h3 align="center"><img src="https://github.com/LHG-Git/2021_Kangnam-univ.-Academic-Seminar-/assets/100845169/cd257d21-1797-4aee-aae1-83141e6f12da"></h3>
<br>

<h3>💭 분석툴 : JupiterLab, Pandas, Numpy, Geopandas, Matplotlib, Seaborn, Sklearn<br><br>
    📅 진행기간 : 2022.11.15 ~ 2022.12.02</h3>

### 👨‍👦‍👦 팀원소개
<table>
<tbody>
  <tr>
    <td align="center"><img src="" width="20px;" alt=""><br /><b>팀장 : 유제우</b></a><br /></td>
    <td align="center"><img src="" width="20px;" alt=""/><br /><b>팀원 : 이희구</b></a><br /></td>
    <td align="center"><img src="" width="20px;" alt=""/><br /><b>팀원 : 정진우</b></a><br /></td>
    <td align="center"><img src="" width="20px;" alt=""/><br /><b>팀원 : 이현중</b></a><br /></td>
   <tr/>
</tbody>
</table>

<br>

<h3 align="center"><img src="https://github.com/LHG-Git/2021_Kangnam-univ.-Academic-Seminar-/assets/100845169/522736f4-ed01-4bfa-a35c-3a9c240726da"></h3><br>

# 🔊 프로젝트 개요
* 국내에서 전기자동차가 인기를 끌고 있음<br>
* 하지만 전기자동차 충전시설 공급이 미비하여 '전기차 충전기 대란' 발생<br>
* 정부의 보조금 지급, 세금 감면 등 지원 정책과 세계적인 고유가 기조까지 맞물림<br>
* 전기자동차 수가 급격히 늘고 있지만, 충전시설 설치는 지지부진<br>
* 전기자동차 충전시설 보급 필요
<br><br>

# 💡 주제 기획
* 2021년 8월 말 기준 전국 전기차 충전기는 19만 5640대로 집계됨<br>
* 문제는 이 중 급속 충전기의 수가 턱없이 부족하다는 점<br>
* 현재 급속 충전기 대수는 1만 3천여대, 완속은 7만 8천 여대로 6배 정도가 많음<br>
* 급속 충전기는 충전하는데 30분, 완속 충전기는 4~5시간이 필요하여 충전 시간 차이가 매우 큼
* 이를 통해 프로젝트에서 진행할 주제를 "전기차 급속 충전소 입지 선정"으로 확정

<br>

# ✔ 분석의 필요성
|배경|필요성|
|------|:------:|
|급속 충전 시설 부족|전기차 활성화의 가장 큰 장벽으로 '급속 충전 시설 부족'이 대표적|
|불편함 호소|전기차 이용객들의 불편함을 해결하기 위해 분석 필요|
|충전소 입지 선정|직장인 인구를 고려한 전기차 충전소의 입지를 선정하기 위해 분석 필요|
|필연적 과정|전기차 활성화를 위해서는 충전소 최적의 입지 선정은 필연적 과정|
|환경 보호|전기차 수요를 늘려 환경 보호에 이바지하기 위해 분석 필요|

<br>

# 🔎 데이터 수집
|데이터셋|출처|
|------|:------:|
|서울시 건강보험 적용인구 구별 통계 데이터|서울 열린데이터광장|
|서울특별시_자치구별 전기차 용도별 등록현황|서울 열린데이터광장|
|급속 충전기 데이터|공공데이터포털|
|전기차 충전소 위치 데이터|공공데이터포털|
|지역인구 데이터(주민등록인구)|공공데이터포털|

<br>

# 🔎 데이터 전처리
|데이터|파생변수 산출방법|파생변수|
|------|:-------------:|:--:|
|TM좌표계|Pyproj|위경도|
|연월별|to_datetime|년, 월, 일|
|충전소 주소|searching|구별 전기차 중전소 개수|

<br><br>

# 📊 EDA(탐색적 데이터 분석)
## 1) 변수별 서울시 구별 밀집도 확인
<h3 align="center"><img src="https://github.com/LHG-Git/project/assets/100845169/704d8af1-2e4c-4968-81f1-7f1a801c2d31"></h3>

* 급속 충전기, 직장인구, 지역인구의 밀집도가 지역별로 비슷한 양상을 띄고 있는 것을 확인
<br><br>

## 2) 급속충천기, 전기차대수, 직장인구, 지역인구 상관관계
<h3 align="center"><img src="https://github.com/LHG-Git/project/assets/100845169/7864b4da-bcef-4d1c-8488-0edbb888b1f8"></h3>

* 전기차 대수 변수가 가장 상관관계가 높은 것을 확인 
* 직장인구와 지역인구의 상관관계가 비슷한 상황인 것을 확인
* 직장인구와 지역인구는 99%의 상관관계가 있어 두 개의 데이터 중 전기차 충전소 입지선정을 위해 직장인구 데이터만 사용

<br><br>

# 📄 최적의 K값 찾기
## 1) Elbow Method
<h3 align="center"><img src= "https://github.com/LHG-Git/project/assets/100845169/f099937f-bccf-4700-a566-cd86d9613058"
></h3>

* 'Elbow Method'를 통해 군집화를 하기 위한 최적의 K값 3을 도출

<br><br>

## 2) K-means Clustering (전기차 대수와 급속 충전기)
<h3 align="center"><img src= "https://github.com/LHG-Git/project/assets/100845169/158aa156-89a3-4abe-9dce-cc028a9c8efc"
></h3>

* 상관관계가 가장 높았던 전기차 대수와 급속 충전기 개수를 군집화해준 결과, 그룹별 큰 특징을 찾지 못하여 직장인구 데이터를 군집화

<br><br>

## 3) K-means Clustering (직장인구와 급속 충전기)
<h3 align="center"><img src= "https://github.com/LHG-Git/project/assets/100845169/e7ee2907-068d-4b34-a506-6b2a1cc746a0"
></h3>

* 파란색 군집인 cluster0는 직장인구에 비해 급속 충전기의 개수가 적당한 군집
> 강북구, 광진구, 금천구, 도봉구, 동대문구, 동작구, 서대문구, 용산구, 종로구, 중구, 중랑구
* 초록색 군집인 cluster1은 직장인구에 비해 급속 충전기의 개수가 충분히 많은 군집
> 강남구, 마포구, 성동구
* 빨간색 군집인 cluster2는 직장인구에 비해 급속 충전기 개수가 적은 군집
> 강동구, 강서구, 관악구, 구로구, 노원구, 서초구, 성북구, 송파구, 양천구, 영등포구, 은평구
<br>

### ※ 따라서 군집결과를 바탕으로 빨간색 군집인 cluster2에 우선적으로 전기차 충전소 입지를 선정해야하는 군집임을 확인

<br><br>

## 4) 빨간색 군집 cluster2 시각화
<h3 align="center"><img src= "https://github.com/LHG-Git/project/assets/100845169/99d82ae9-b910-485f-ad10-38d35db29165"
></h3>

* 왼쪽 시각화 자료는 빨간색 군집인 cluster2에 포함된 지역을 확인해 준 것
* 오른쪽 시각화 자료는 직장인구와 급속 충전기 개수의 비율을 계산한 것
* 빨간색이 진할수록 비율이 높은 지역으로, 급속 충전기가 부족한 지역에 해당

<br>

# 🖥 분석결과
<h3 align="center"><img src= "https://github.com/LHG-Git/project/assets/100845169/007c1cf4-72f4-413e-9d59-95eb03d88e0d"></h3>

* 비율이 가장 높은 곳이 급속 충전기가 부족한 지역인것을 확인
* 급속 충전기 대비 직장인구가 많은 지역 중 비율이 가장 높은 지역 '관악구', '구로구', '은평구' 확인
* '관악구', '은평구', '구로구'에 급속 충전기를 우선적으로 입지를 선정



