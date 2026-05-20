# 🏘️ 서울시 주거취약지역 기반 모아센터 입지 우선순위 분석

### Data-Driven Site Prioritization for Additional Moa Centers in Seoul
> 주거 취약성, 정책 수요, 공급 공백을 기반으로 서울시 모아센터 추가 입지 우선순위를 분석한 프로젝트
---

## Overview

본 프로젝트는 서울시 행정동 단위의 주거 취약성(HVI), 정책 수요, 기존 모아센터 접근성을 종합적으로 분석하여 모아센터 추가 설치 우선순위를 도출한 공간 데이터 기반 정책 분석 프로젝트입니다.

단순히 취약한 지역을 찾는 데서 끝나지 않고,

- 주거 취약성
- 정책 수요
- 기존 공급 공백
- 접근성 개선 효과

를 함께 고려하여,

> "어디에 모아센터를 우선적으로 추가 배치하는 것이 타당한가?"

를 데이터 기반으로 분석하는 것을 목표로 했습니다.

---

## Key Features

- 행정동 단위 Housing Vulnerability Index(HVI) 구축
- 정책 수요 기반 지역 우선순위 산출
- 기존 모아센터 접근성 분석
- 공급 공백(Supply Gap) 기반 후보지 선정
- 거리 기반 접근성 시뮬레이션
- Random Allocation 대비 정책 제안안 효과 검증
- 공간 시각화 기반 최종 후보지 분석

---

## Tech Stack

#### Language

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" height="28"/>
</p>

---

#### Data Processing & Analysis

<p>
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" height="28"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" height="28"/>
  <img src="https://img.shields.io/badge/GeoPandas-139C5A?style=flat-square" height="28"/>
</p>

---

#### Spatial Analysis & Simulation

<p>
  <img src="https://img.shields.io/badge/Spatial%20Analysis-1E88E5?style=flat-square" height="28"/>
  <img src="https://img.shields.io/badge/Accessibility%20Simulation-5E35B1?style=flat-square" height="28"/>
  <img src="https://img.shields.io/badge/HVI-6A1B9A?style=flat-square" height="28"/>
</p>

---

#### Visualization

<p>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square" height="28"/>
  <img src="https://img.shields.io/badge/Seaborn-0C7BDC?style=flat-square" height="28"/>
</p>

---

## Analysis Framework

### 1️⃣ Housing Vulnerability Index (HVI)

행정동 단위의 주거 취약성을 정량화하기 위해 다음 요소를 활용했습니다.

- 저가 주거 비율
- 노후 주택 비율
- 주거 밀집도

이를 통해 저가 주거, 노후도, 밀집도가 동시에 높은 지역을 주거취약지역으로 정의했습니다.

---

### 2️⃣ Policy Demand Index

모아센터의 정책적 필요성을 반영하기 위해 다음 지표를 활용했습니다.

- 고령층 관련 지표
- 장애인 관련 지표
- 저소득층 관련 지표
- 생활환경 지표
- 재난·안전 지표
- 범죄 취약성 지표

---

### 3️⃣ Accessibility & Supply Gap

기존 모아센터 공급 현황과 접근성을 함께 고려했습니다.

- 기존 모아센터 위치 행정동 제외
- 행정동 대표점 기준 거리 계산
- 접근성이 낮은 행정동 식별
- 공급 공백 지역 분석
- 추가 설치 시 접근성 개선 효과 시뮬레이션

---

## Simulation Scenarios

| Scenario | Description |
|---|---|
| S0 | Existing 14 Centers (Baseline) |
| S1 | Random 14 Allocation (1,000 Iterations) |
| S2 | Top 14 by Demand Index |
| S3 | Top 14 by Final Index |
| S4 | Final Proposal with HVI Filter & Spillover Effect |

---

## Main Findings

- 기존 공급 대비 접근성 취약 지역 식별
- 공급 공백 기반 후보지 도출
- Random Allocation 대비 공간적 개선 효과 확인
- 정책 수요와 주거 취약성을 동시에 반영한 입지 선정 가능성 검증
- 추가 배치 시 접근성 개선 효과 확인

---

## Directory Structure

```bash
(수정예정)
```

---

## Main Scripts

### `build_candidate_pool.py`

- 기존 모아센터 행정동 제외
- HVI = 0 제외
- 정책 수요 하위 지역 제외
- 후보지 목록 생성
- 필터링 로그 저장

---

### `simulation.py`

- 기존 접근성 계산 (S0)
- S1~S4 시나리오 비교
- 랜덤 배치 대비 효과 분석
- 접근성 개선 효과 계산

---

### `최종시각화_0421.py`

- 행정동별 지표 시각화
- 최종 후보지 지도화
- 접근성 개선 결과 시각화
- 발표용 결과 이미지 생성

---

## Data Sources

- 서울시 빅데이터 캠퍼스
- 공공데이터포털
- 서울시 건축물대장 데이터
- 서울시 행정동 경계 데이터
- 기존 모아센터 위치 정보

⚠️ 일부 원본 데이터는 반출 정책상 공개가 제한될 수 있습니다.

---

## Limitations

- 행정동 대표점 기반 거리 계산 사용
- 실제 보행 접근성과 차이 가능성 존재
- 일부 데이터는 가공 지표 형태 활용
- 실제 설치 가능성은 추가 행정 검토 필요

---

## Conclusion

본 프로젝트는 주거 취약성, 정책 수요, 공급 공백을 함께 고려하여 서울시 내 모아센터 추가 설치 우선순위를 도출하고,  
시뮬레이션을 통해 실제 접근성 개선 효과를 검증하는 데 초점을 두었습니다.
단일 지표 기반 접근이 아닌 공간적 공급 불균형과 정책 수요를 함께 반영했다는 점에서 공공정책 기반 공간 데이터 분석 사례로 의미가 있습니다.
