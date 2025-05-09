# wh_06_1st_team5

## 자취 구역 추천 서비스 - 어디 살까
---
- 참여인원 : 장윤수, 문해성, 오요셉(팀장)
- 프로젝트 기간 : 5/7 ~ 5/9
---
### 1. 프로젝트 개요
---
#### 목표 : 
- 사회초년생들을 위한 거주지 추천
- 치안, 소음, 청결도 등과 같은 특정 행정구역의 분위기 및 
  출퇴근 소요 시간, 예산에 따른 거주지 추천 서비스

#### 기획 사유 : 
- 일자리와 인구의 밀집

![Image](https://github.com/user-attachments/assets/745eeeae-a645-4836-97d5-62d1009115e9)

- 서울특별시의 높은 월세 
- 거주 경험 부재로 인한 지역별 정보 부족

#### 시장 분석 :
- 대상 : 18세 ~ 34세의 청년층
 - 18세 ~ 34세 인구이동 현황
 - 18세 ~ 34세 전체 인구 현황
---
### 2. 서비스 개요
---
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
### 3. Sequence Diagram
---

![Image](https://github.com/user-attachments/assets/7c4fe7cf-81b4-4154-9b52-48da47d64856)

---
### 4. ERD | 테이블 정의서
---
[테이블정의서.pdf](https://github.com/user-attachments/files/20114487/default.pdf)


![Image](https://github.com/user-attachments/assets/cb7b1ff6-1663-478e-b1e4-57ef97d779c4)

---
### 5. 기술 스택
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
