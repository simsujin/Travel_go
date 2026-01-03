# ✈️ TravelGo  
### Foreigner-Friendly Travel Assistant for Korea

![Flutter](https://img.shields.io/badge/Flutter-02569B?logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?logo=dart&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?logo=supabase&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)

---

## 📌 프로젝트 개요

**TravelGo**는 한국을 방문하는 외국인 여행자가 겪는  
**정보 파편화 · 낮은 신뢰도 · 즉각적인 의사결정의 어려움**을 해결하기 위해 기획된  
**여정 기반 한국 여행 통합 가이드 서비스**입니다.

여행객은 지도, 영상, 검색, SNS를 각각 오가며 정보를 소비하고  
그 과정에서 **경험의 흐름이 끊어지고 결정 피로도**가 누적됩니다.

TravelGo는  
> **“여행 중 끊기지 않는 결정의 흐름”**  
을 핵심 가치로,  
사용자의 **위치 · 시간 · 일정 맥락**에 맞는 정보를 한 흐름으로 제공합니다.

---

## 🎯 프로젝트 목표 (Project Goals)

1. 여행 중 **정보 탐색 → 결정 → 이동 → 경험** 흐름 단절 최소화
2. 한국 여행에 특화된 **신뢰도 높은 로컬 데이터** 제공
3. 일정 변경 상황에서도 즉시 대응 가능한 **컨텍스트 기반 추천**
4. 외국인 관점에서 이해하기 쉬운 **설명 중심 UX** 구현
5. 확장 가능한 구조(제휴/추천/AR/ML)를 고려한 서비스 설계

---

## 📊 성과 지표 (KPI)

| 구분 | KPI 지표 | 목표 |
|---|---|---|
| 사용성 | 추천 클릭률 (CTR) | ≥ 30% |
| 경험 흐름 | 추천 → 장소 상세 전환율 | ≥ 40% |
| 만족도 | 추천 결과 저장(북마크) 비율 | ≥ 25% |
| 효율 | 평균 의사결정 시간 감소 | ≥ 20% |
| 신뢰도 | 공공/로컬 데이터 기반 장소 사용률 | 지속 증가 |

---

## 🏗️ 시스템 아키텍처 개요

- **Client** : Flutter (iOS / Android)
- **Backend** : FastAPI
- **DB** : PostgreSQL (Supabase)
- **ML** : scikit-learn
- **External APIs**  
  - Google / Kakao / Naver Map  
  - 공공데이터포털(data.go.kr)  
  - OpenAI API
- **Collaboration** : Figma / GitHub / Notion

---

## 🔁 전체 워크플로우

1. 사용자가 Flutter 앱에서 장소 탐색 / 추천 요청
2. FastAPI 서버가 요청 수신
3. 외부 API(지도·공공데이터) 호출 및 데이터 정제
4. PostgreSQL에 저장된 사용자/여정/로그 데이터 조회
5. scikit-learn 기반 추천 로직 실행
6. OpenAI API로 추천 이유 및 요약 생성
7. 정제된 결과를 Flutter 앱에 전달

---

## 🧩 기술 스택 상세

### Client App
- **Flutter (Dart)**
  - 여행 중 사용성을 고려한 단순하고 명확한 UI
- **주요 플러그인**
  - `geolocator` : 위치 기반 기능
  - `ar location viewer` : AR 기반 위치 경험 확장

### Backend / DB / ML
- **FastAPI**
  - API 라우팅, 외부 API 통합, 데이터 정제
- **Supabase**
  - 인증 및 DB 인프라 구축
- **PostgreSQL**
  - 유저, 여정, 장소, 로그 데이터 관리
- **scikit-learn**
  - 추천 점수 계산 및 랭킹 모델

### External APIs
- **Google / Kakao / Naver Map**
  - 한국 로컬 지도 및 장소 정보 보완
- **공공데이터포털**
  - 관광/시설 정보의 신뢰도 확보
- **OpenAI API**
  - 자연어 요약 및 추천 설명 생성

---

## 🧠 나의 역할 (Role)

- 서비스 기획 및 문제 정의
- 핵심 UX 컨셉 및 사용자 여정 설계
- 화면 구조 및 디자인 시스템 설계 (Figma)
- Flutter 기반 UI 구현
- FastAPI 구조 설계 및 API 연동
- DB 구조 설계 및 데이터 흐름 정의
- 추천 로직 설계 및 ML 연동 구조 기획
- 전체 아키텍처 통합 및 개선

---

## 🧯 트러블슈팅 (Troubleshooting)

### 1️⃣ 외부 지도 데이터 신뢰도 문제
- **문제**: Google Maps 단독 사용 시 한국 장소 정보 정확도 부족
- **해결**:  
  - Kakao / Naver / 공공데이터 병행 사용  
  - 서버에서 데이터 정제 및 우선순위 로직 적용

---

### 2️⃣ 여행 중 정보 과다 노출
- **문제**: 한 화면에 너무 많은 정보 → 사용 피로 증가
- **해결**:  
  - 위치/시간/일정 기반으로 노출 정보 최소화  
  - “지금 필요한 정보만” 제공하는 UX 설계

---

### 3️⃣ 추천 결과의 신뢰 부족
- **문제**: AI 추천에 대한 불신
- **해결**:  
  - 추천 이유를 자연어로 설명  
  - 공공데이터·지도 출처를 함께 제시

---

### 4️⃣ 확장성 없는 초기 설계 리스크
- **문제**: 기능 추가 시 구조 변경 위험
- **해결**:  
  - Client / Backend / ML / External API 명확히 분리  
  - AR, 제휴, 광고 기능을 플러그인 형태로 확장 가능하게 설계

---

## 🚀 확장 방향 (Roadmap)

- 세션/컨텍스트 기반 추천 고도화
- AR 기반 실시간 여행 안내
- 관광청·도시 브랜드 제휴 모델
- 교통·숙박 플랫폼 연동
- 다국어 UX 및 문화 맥락 반영 강화

---

## 🙌 Contact

**Sophie Sim**  
Interactive / UX-Oriented Designer & Developer  
📍 Korea · Canada  
🔗 Portfolio & GitHub: (추가 예정)

---

> 본 프로젝트는 LG DX School DX Project의 일환으로 진행되었으며,  
> 개인 포트폴리오 목적으로 정리된 결과물입니다.
