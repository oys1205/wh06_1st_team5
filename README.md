# wh_06_1st_team5

# 어디 살까
---
## 프로젝트 기획서
---
### 1. 프로젝트 개요
---
#### 목표 : 
- 사회초년생들을 위한 거주지 추천
- 치안, 소음, 청결도 등과 같은 특정 행정구역의 분위기 및 
  출퇴근 소요 시간, 예산에 따른 거주지 추천 서비스

#### 근거 : 
- 2030의 상경 (지방 지역주민 이탈, 수도권 전입)
- 일자리와 인구의 밀집
- 서울특별시 월세 금액 우상향
- 거주 경험 부재로 인한 지역별 정보 부족

#### 시장 분석 :
- 대상 : 18세 ~ 34세의 청년층
 - 18세 ~ 34세 인구이동 현황
 - 18세 ~ 34세 전체 인구 현황

#### 상세 서비스 개요
- 분위기 타입 필터링
    - 행정구역명을 기반으로 Google Custom Search API 호출
    - 감정분석, 텍스트 빈도수 분석을 통한 사용자 설정 분위기 타입으로 필터링

- 출퇴근 시간 필터링
    - Google Maps API를 사용한 회사 기준 사용자 설정 출퇴근 소요 시간 필터링
    - 설정 소요시간을 기준으로 바운더리 생성 및 바운더리 내 거주지 추천

- 예산 필터링
    - 국토교통부 실거래가 공개시스템 조회를 통한 행정구역별, 면적 구간별, 주거 형태별 평균 월세 추출
    - 사용자 설정 예산에 따른 거주지 추천

- 커뮤니티 형성
    - 행정구역별 게시판 운영
    - 행정구역의 분위기, 교통, 인프라 등 복합적인 평가 시스템 운영
---
### 2. 기술 스택
---
|구분|기술|
|------|---|
|프론트엔드|Flutter|
|백엔드 API 서버|FastAPI|
|DB|PostgreSQL, MongoDB|
|파일저장소|AWS S3|
|크롤링|Selenium, BeautifulSoup, pandas|
|사용 API|Google Places API, Google Maps API, Google Custom Search API|
|배포 플랫폼|Render, AWS Lightsail (초기), AWS EC2/ECS (확장 시)|
|유저 인증|Firebase Auth|
|스케쥴링|APScheduler|
---
### 3. 데이터 관리
---
[User Mobile/Web App]

↓

[FastAPI Backend API]

↓

- 주요 백엔드 기능

1. 회원가입, 검색 필터 저장 (PostgreSQL)

2. 회사 주소 → 위도경도 변환 (Google Maps)

3. 통근 다각형 생성 (Google Directions)

4. 다각형 내 행정구역 파악 (GeoReverse API)

5. 지역 POI/인프라 수집 (Google Places)

6. 지역 리뷰/분위기 크롤링 (Custom Search)

7. 실거래가 크롤링 (Selenium → Pandas → DB)

8. 필터 조건에 맞는 지역 추천 (쿼리/분석)

↓

[PostgreSQL] ← 구조화된 데이터 (검색 기록, 실거래가 등)

[MongoDB]   ← 크롤링 텍스트, 감정분석 결과, 자유 게시판 등

[Firebase Storage] ← 이미지/리포트/지도 등 파일 저장

↓

[Flutter / React 앱에 시각화 및 추천결과 제공]

#### ERD
![Image](https://github.com/user-attachments/assets/cb7b1ff6-1663-478e-b1e4-57ef97d779c4)


