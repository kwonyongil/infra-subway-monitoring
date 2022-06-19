<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-%3E%3D%205.5.0-blue">
  <img alt="node" src="https://img.shields.io/badge/node-%3E%3D%209.3.0-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/next-step/atdd-subway-service">
</p>

<br>

# 인프라공방 샘플 서비스 - 지하철 노선도

<br>

## 🚀 Getting Started

### Install
#### npm 설치
```
cd frontend
npm install
```
> `frontend` 디렉토리에서 수행해야 합니다.

### Usage
#### webpack server 구동
```
npm run dev
```
#### application 구동
```
./gradlew clean build
```
<br>


### 1단계 - 웹 성능 테스트
1. 웹 성능예산은 어느정도가 적당하다고 생각하시나요

### A. 예비분석, B 경쟁사 분석

#### 나의사이트 https://kwonyongil-infra.kro.kr
##### 나의사이트 (정량)
| 기기    | 이미지 최대 크기 | 웹 글꼴 최대 크기 | 글꼴 최대 갯수 | 스크립트 최대 크기 | 스크립트 최대 갯수 | HTML, CSS 최대 크기 | 동영상 최대 크기 |
|-------|-----------|------------|----------|------------|------------|-----------------|-----------|
| Pc/Mo | 4.6kB     | 277kB      | 12       | 2.2MB      | 2          | 38.2kB          | 0 B       |

##### 나의사이트 (시간)
| 기기  | FCP   | LCP   | TTI   | TBT   | CLS   | Speed Index |
|-----|-------|-------|-------|-------|-------|-------------|
| Pc  | 2.7s  | 2.8s  | 2.8s  | 50ms  | 0.004 | 2.7s        |
| Mo  | 14.6s | 15.2s | 15.2s | 550ms | 0.042 | 14.6s       |
##### 나의사이트 (규칙)
- Pc : 68점
- Mo : 32점

#### 경쟁사 분석
##### 서울교통공사 (정량)
| 기기    | 이미지 최대 크기 | 웹 글꼴 최대 크기 | 글꼴 최대 갯수 | 스크립트 최대 크기 | 스크립트 최대 갯수 | HTML, CSS 최대 크기 | 동영상 최대 크기 |
|-------|-----------|------------|----------|------------|------------|-----------------|-----------|
| Pc/Mo | 12.7kB    | 27.2kB     | 26       | 214kB      | 9          | 127kB           | 0 B       |

##### 서울교통공사 (시간)
| 기기  | FCP  | LCP  | TTI  | TBT    | CLS   | Speed Index |
|-----|------|------|------|--------|-------|-------------|
| Pc  | 1.6s | 3.6s | 2.0s | 80ms   | 0.014 | 2.5s        |
| Mo  | 6.9s | 7.6s | 9.6s | 1620ms | 0     | 9.3s        |
##### 서울교통공사 (규칙)
- Pc : 63점
- Mo : 25점

##### 네이버지도 (정량)
| 기기    | 이미지 최대 크기 | 웹 글꼴 최대 크기 | 글꼴 최대 갯수 | 스크립트 최대 크기 | 스크립트 최대 갯수 | HTML, CSS 최대 크기 | 동영상 최대 크기 |
|-------|-----------|------------|----------|------------|------------|-----------------|-----------|
| Pc/Mo | 67.8kB    | 0kB        | 0        | 87.5kB     | 12         | 52.0kB          | 0 B       |

##### 네이버지도 (시간)
| 기기  | FCP  | LCP  | TTI  | TBT   | CLS   | Speed Index |
|-----|------|------|------|-------|-------|-------------|
| Pc  | 0.5s | 1.6s | 0.7s | 0ms   | 0.006 | 2.3s        |
| Mo  | 2.2s | 7.9s | 6.6s | 330ms | 0.03  | 6.4s        |

##### 네이버지도 (규칙)
- Pc : 89
- Mo : 56

##### 카카오맵 (정량)
| 기기    | 이미지 최대 크기 | 웹 글꼴 최대 크기 | 글꼴 최대 갯수 | 스크립트 최대 크기 | 스크립트 최대 갯수 | HTML, CSS 최대 크기 | 동영상 최대 크기 |
|-------|-----------|------------|----------|------------|------------|-----------------|-----------|
| Pc/Mo | 67.8kB    | 0kB        | 0        | 87.5kB     | 12         | 52.0kB          | 0 B       |

##### 카카오맵 (시간)
| 기기  | FCP  | LCP  | TTI  | TBT  | CLS   | Speed Index |
|-----|------|------|------|------|-------|-------------|
| Pc  | 0.5s | 1.0s | 0.6s | 0ms  | 0.039 | 2.7s        |
| Mo  | 1.7s | 5.0s | 4.2s | 90ms | 0.05  | 7.0s        |

##### 카카오맵 (규칙)
- Pc : 92
- Mo : 72

#### 결론
- Pc 나의 사이트 : 68점
- Mo 나의 사이트 : 32점
- Pc 경쟁사 평균 81점, 최고 점수 92
- Mo 경쟁사 평균 51점, 최고점수 72
경쟁사 대비 20% 이상의 성능을 내어 경쟁력을 확보할 수 있도록합니다.
현재 가장 높은 점수인 경쟁사 카카오 맵보다 높을 수 있도록 목표를 잡습니다. (92점 이상)

- C. 성능 기준 설정
- FCP 2.5초 미만으로 정합니다.
- TTI 3초 미만으로 정합니다.
- 리소스 크기를 200Kb 미만으로 제한합니다.


- D. 우선 순위
- 1. TTI : 경로 조회를 하는 것이 주 목적이기 때문에 TTI가 우선되어야 합니다.
- 2. FCP : 이탈 방지를 위해 FCP가 그 다음 (측정된 FMP가 있다면 FMP)
- 3. 기타 고려


4. 웹 성능예산을 바탕으로 현재 지하철 노선도 서비스는 어떤 부분을 개선하면 좋을까요

- (1) js 용량을 줄입니다.
  - /js/vendors.js 용량을 줄인다. 
  - 분석결과 2,125.4 kB -> 637.3kB 가능 (더 줄여서 목표치를 달성하도록 한다.)
  - /js/main.js 용량을 줄인다. 
  - 분석결과 172.3 kB -> 61.8kB 가능
- (2) 텍스트 기반 리소스 압축 이용 (gzip, deflate, brotli)
- (3) 정적 리소스들을 CDN 캐시를 이용할 수 있도록 합니다.
- (4) 적절한 리소스 지연 로딩 
- (5) 웹폰트가 로드되는 동안 텍스트가 표시될 수 있도록 합니다.

---

### 2단계 - 부하 테스트 
1. 부하테스트 전제조건은 어느정도로 설정하셨나요
#### Target(대상) 시스템의 범위 :
- (1) Reverse Proxy
- (2) Tomcat
- (3) MySQL

#### 부하 테스트 시 저장될 데이터 건수 및 크기
- 지하철 노선 : 23개
- 지하철 역 : 616개
- 구간 : 340개


#### 예상 DAU
네이버 지도 1392만 MAU
카카오 맵 600만 MAU
초기 단계임을 고려해서 450만 MAU / 30일

15만 DAU로 예상한다.

#### 피크 시간대의 집중률(최대 트래픽 / 평소 트래픽)
- 08:00 ~ 09:00, 17:00 ~ 19:00
- 출퇴근 시간대와 막차 시간을 피크 시간대로 설정
- (최대 트래픽 8만 / 평소 트래픽 2만), 4배정도
- https://data.seoul.go.kr/dataList/OA-12252/S/1/datasetView.do 참고

#### 1명당 1일 요청수
- 메인 페이지, 로그인 페이지, 로그인 요청, 즐겨찾기 페이지, 경로 검색 페이지, 경로 검색
- 대략 6회 요청

#### Throughput
- Throughput : 1일 평균 rps ~ 1일 최대 rps
- 10.41 rps ~ 41.64 rps

  - 1일 사용자 수(DAU) x 1명당 1일 평균 접속 수 = 1일 총 접속 수
  - 15만 x 6 = 90만

  - 1일 총 접속 수 / 86,400 (초/일) = 1일 평균 rps
  - 90만 / 86400 = 10.41 rps

  - 1일 평균 rps x (최대 트래픽 / 평소 트래픽) = 1일 최대 rps
  - 10.41rps x 4 = 41.64 rps

#### 시나리오 대상:
- 접속 빈도가 높은 기능(페이지) : 메인 페이지
- 데이터를 갱신하는 페이지 : 나의 정보 수정
- 데이터를 조회하는데 여러 데이터를 참조하는 페이지 : 경로 검색
- 시나리오 메인 페이지 접속 -> 로그인 -> 즐겨찾기 -> 경로 검색
- (나의 정보 수정은 자주 발생하지 않으므로 이번 시나리오에서는 제외)

#### Latency
- Latency : 100ms

#### VUser 구하기
- VUser = (목표 rps * T) / R
- 가령, 두개의 요청 (R=2)이 있고, 왕복시간이 0.5s, 지연시간이 1초라고 가정할 때 (T=2), 계산식은 아래와 같다.
- T = (R * http_req_duration) (+ 1s)
- VU = (300 * 2) / 2 = 300

- 본 미션 전제조건의 경우 아래와 같다.
  - 1.6 = (6 * 0.1) + 1 
  - VUser = (목표 rps * T) / R
  - min VUser: (10.41 * 1.6) / 6 = 대략 3
  - max VUser: (41.64 * 1.6) / 6 = 대략 12




2. Smoke, Load, Stress 테스트 스크립트와 결과를 공유해주세요

---


### 3단계 - 로깅, 모니터링
1. 각 서버내 로깅 경로를 알려주세요

2. Cloudwatch 대시보드 URL을 알려주세요
