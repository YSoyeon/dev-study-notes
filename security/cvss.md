# CVSS

> 공통 취약점 등급 시스템

## CVSS 메트릭 그룹

CVSS 점수는 기초, 시간, 환경 등 3가지 메트릭 그룹으로 구성된다.

⚙️ 기초 메트릭

- 취악점의 특성을 나타낸다.
- 3가지 하위 요소(악용 가능성, 범위, 영향)으로 구성된다.

⚙️ 시간 메트릭

- 시간에 따라 변화하는 취약점의 특성을 반영한다.
- 현재 악용가능성과 대응 요소의 가용성을 중요하게 다룬다.
- 시간 메트릭의 하위 구성요소에는 악용 코드의 성숙도, 대응 수준, 보고 신뢰도가 있다.

⚙️ 환경 메트릭

- 사용자의 환경을 고려한 취약점의 특성을 나타낸다.

### CVSS 점수

- CVSS 점수는 0.0~10.0으로 부여한다.
  (v3 기준) 위험도
  - None : `0.0`
  - Low : `0.1` ~ `3.9`
  - Medium : `4.0` ~ `6.9`
  - High : `7.0` ~ `8.9`
  - Critical : `9.0` ~ `10.0`
- 기초 점수(악용가능성 점수 + 영향 점수) 는 필수점수이며, 시간 및 환경 점수는 선택사항이다. <br />
  (다만, 기초 점수는 시간 및 환경 메트릭을 통해 조정 가능하다.)

## 3.1 과 4.0 차이점

### ver 3.1

> 2019년 6월 10일 출시

### ver 4.0

> 2023년 10월 1일 출시

## 참고

- [CVSS: 공통 취약점 등급 시스템(CVSS)에 대해 알아야 하는 모든 것
  ](https://www.appsealing.com/kr/cvss-blog/)

- [CVSS v3.1 Base Score Calculator
  ](https://itschool-info-lab.github.io/cvss/)