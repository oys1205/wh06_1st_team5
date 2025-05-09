# wh_06_1st_team5

# 싱크홀 트래커
---
## 프로젝트 기획서
### 1. 프로젝트 개요
- 주제 : 
    - 사회초년생들을 위한 거주지 추천
- 근거 : 
    - 2030의 상경 (지방 지역주민 이탈, 수도권 전입)
    - 일자리와 인구의 밀집
    - 서울특별시 월세 금액 우상향
    - 거주 경험 부재로 인한 지역별 정보 부족
- 목표 : 
    - 치안, 소음, 청결도 등과 같은 특정 행정구역의 분위기 및 
      출퇴근 소요 시간, 예산에 따른 거주지 추천
- 시장 분석 :
    - 18세 ~ 34세 인구이동 현황
---
### 2. 기술 스택
- 프론트엔드 :
    - Flutter
- 백엔드 API 서버 :
    - FastAPI
- DB :
    - PostgreSQL (정형데이터)
    - MongoDB (비정형데이터)
- 파일저장소 :
    - AWS S3
- 크롤링 :
    - Selenium, BeautifulSoup, pandas
- 사용 API :
    - Google Places API
    - Google Maps API
    - Google Custom Search API
- 배포 플랫폼 :
    - Render, AWS Lightsail (초기)
    - AWS EC2/ECS (확장 시)
- 유저 인증 :
    - Firebase Auth
- 스케쥴링 :
    - APScheduler
---
### 3. 데이터 수집

#### ERD
![Image](https://github.com/user-attachments/assets/cb7b1ff6-1663-478e-b1e4-57ef97d779c4)
### 4. 데이터 분석 및 모델링

