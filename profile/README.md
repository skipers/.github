# SKIPA: 특허 Life Cycle 관리 서비스

> **SK IP Agent, SKIPA**  
> 특허 Life Cycle 관리와 연차료 납부 전 재평가 의사결정을 지원하는 AI 기반 특허 관리 서비스입니다.

<br/>

## 👥 Team

**SKIPERS**는 SKALA AI 3기 8팀입니다.  
우리는 사내 특허 재평가 과정에서 발생하는 자료 분산, 추상적인 평가 기준, 담당자 변경에 따른 전문성 공백 문제를 해결하기 위해 **SKIPA(SK IP Agent)**를 개발하고 있습니다.

<br/>

## 🚀 Service Overview

**SKIPA**는 회사에서 출원한 특허에 대해 가치 평가와 Life Cycle 관리를 지원하는 AI 서비스입니다.

기존 특허 재평가 과정에서는 분기마다 연차료 납부 대상 특허를 검토하고, 법무팀이 관련 사업부에 평가를 요청한 뒤 사업부가 유지 또는 포기 의견을 제출합니다. 이 과정에서 평가 기준이 주관적이고, 참고 자료가 여러 곳에 흩어져 있으며, 조직 개편 이후에는 담당자 부재로 전문적인 판단이 어려워질 수 있습니다.

SKIPA는 이를 해결하기 위해 다음 기능을 제공합니다.

- 특허청·한국발명진흥회 IP 가치평가 실무가이드 기반의 객관적인 평가 기준 제공
- 특허 원문, 메타데이터, 외부 자료를 활용한 AI 기반 가치 평가
- 유사 특허, 관련 제품, 사내 프로젝트 정보를 함께 반영한 판단 보조 자료 제공
- 법무팀과 사업부서의 검토 요청, 진행 현황 추적, 유지/포기 의견 제출 흐름 지원
- 평가 결과와 참고 자료를 통합한 특허 평가 보고서 생성

<br/>

## 🧩 Core Features

### Legal Team

법무팀은 특허 등록부터 재평가 요청, 진행 현황 관리까지 전체 운영 흐름을 관리합니다.

- 특허 원본 PDF 업로드 또는 직접 입력을 통한 신규 특허 등록
- 분기별 재평가 대상 특허 관리
- 특허별 관련 사업부 배정 및 검토 요청 전송
- 사업부별 처리 현황과 미회신 특허 추적
- 신규 유지/포기 결정 결과 확인

### Business Department

사업부서는 배정받은 특허를 검토하고, AI 보고서와 특허 원문을 바탕으로 유지 또는 포기 의견을 제출합니다.

- 배정받은 특허 검토 요청 확인
- 특허 원문 및 AI 평가 보고서 열람
- 유지/포기 결정 및 코멘트 제출
- 결정 내역 확인

<br/>

## 🤖 AI Evaluation Pipeline

SKIPA의 AI 평가 파이프라인은 특허 원문과 메타데이터를 바탕으로 평가를 수행하고, 점수와 근거를 포함한 보고서를 생성합니다.

```text
특허 원문/메타데이터 수집
→ 가치 평가 수행
→ 점수화 및 근거 생성
→ 재평가 보고서 생성
```

평가 항목은 특성에 따라 다음 방식으로 분류하여 처리합니다.

| Evaluation Type | Description | Example |
|---|---|---|
| 자동 계산 | 특허 메타데이터를 활용해 정량 점수 산출 | 피인용 횟수, 청구항 수, 출원인 수, 분쟁 이력 |
| LLM 분석 | 청구항과 명세서를 분석해 체크리스트 기반 점수 산출 | 권리범위 적절성, 모방 난이도, 권리의 추상성 |
| 웹 검색 | 외부 자료를 수집해 시장성·경쟁성 판단 | 대체 기술, 고객 영향도, 특허 출원 활성도 |
| 하이브리드 | LLM 분석과 웹 검색을 함께 활용 | 차별성 및 파급성, 무효 가능성, 혁신성 |

<br/>

## 📄 AI Report

SKIPA는 평가 결과를 단순 점수로만 제공하지 않고, 근거와 참고 자료를 포함한 보고서 형태로 제공합니다.

보고서는 다음 항목으로 구성됩니다.

1. **평가 요약**  
   기술성, 권리성, 시장성 및 사업성 기준의 점수와 종합 의견을 제공합니다.

2. **평가 기준별 상세 점수**  
   세부 평가 항목, 점수, 산출 방식, 판단 요지를 표 형태로 제공합니다.

3. **사내 프로젝트 활용 현황**  
   사내 문서를 기반으로 해당 특허가 활용되고 있는 프로젝트 정보를 제공합니다.

4. **유사 특허 분석**  
   KIPRIS 기반 유사 특허 정보를 활용하여 대상 특허와 경쟁 특허의 유사점, 차별점, 권리 범위를 비교합니다.

5. **추가 확인 필요 사항**  
   점수가 낮은 항목과 사업부 내부 자료로 교차 검토가 필요한 내용을 정리합니다.

6. **참고 문헌**  
   가치 평가 과정에서 활용한 참고 자료를 출처별로 정리합니다.

<br/>

## 📦 Repositories

| Repository | Description | Tech Stack |
|---|---|---|
| [skipa-frontend](https://github.com/skipers/skipa-frontend) | SKIPA 서비스의 사용자 화면을 담당하는 프론트엔드 애플리케이션 | Vue |
| [skipa-backend](https://github.com/skipers/skipa-backend) | 특허 관리, 재평가 요청, 의사결정 흐름을 처리하는 백엔드 API 서버 | Spring Boot |
| [skipa-ai-server](https://github.com/skipers/skipa-ai-server) | 특허 가치 평가, 유사 특허 분석, AI 보고서 생성을 담당하는 AI 서버 | FastAPI |
| [.github](https://github.com/skipers/.github) | 조직 소개 README와 공통 GitHub 템플릿을 관리하는 레포지토리 | GitHub Templates |

<br/>

## 🛠️ Tech Stack

### Frontend

![Vue](https://img.shields.io/badge/Vue-4FC08D?style=flat-square&logo=vue.js&logoColor=white)

### Backend

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)

### AI Server

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenAI](https://img.shields.io/badge/GPT--4o-412991?style=flat-square&logo=openai&logoColor=white)

### External Data & Search

![KIPRIS](https://img.shields.io/badge/KIPRIS-1F4E79?style=flat-square)
![Tavily](https://img.shields.io/badge/Tavily-111827?style=flat-square)

### Collaboration

![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

<br/>

## 🤝 Collaboration Rules

SKIPERS는 이슈 기반으로 작업을 관리하고, 아래 흐름으로 협업합니다.

```text
이슈 생성 → 브랜치 생성 → 작업 → 커밋 → PR 생성 → 리뷰 → dev 병합
```

자세한 협업 규칙은 [CONTRIBUTING.md](../CONTRIBUTING.md)를 참고해 주세요.

<br/>

## 🏷️ Label Convention

| Label | Color | Description |
|---|---|---|
| `✨ feature` | `#B6E1C9` | 새로운 기능 추가 또는 기존 기능 개선 |
| `🐛 bug` | `#F4A6A6` | 오류, 예외, 예상과 다른 동작 수정 |
| `♻️ refactor` | `#D6C2F0` | 기능 변경 없는 코드 구조 및 품질 개선 |
| `⚙️ infra` | `#F9B572` | 배포, CI/CD, Docker, 서버, 환경 설정 관련 작업 |
| `📝 docs` | `#AFCBFF` | README, API 문서, 가이드 등 문서 작업 |
| `🔧 chore` | `#BFDADC` | 기타 설정, 의존성 관리, 템플릿 추가 등 프로젝트 관리 작업 |

<br/>

## 🌿 Branch Convention

브랜치는 이슈 번호를 포함하여 아래 형식으로 생성합니다.

```text
{type}/{issue-number}-{short-description}
```

예시:

```text
feat/12-patent-search
fix/21-login-token-error
refactor/30-patent-service
chore/40-update-readme
```

<br/>

## 📌 Commit Convention

커밋 메시지는 아래 형식을 따릅니다.

```text
type: 작업 내용
```

예시:

```text
feat: 특허 목록 조회 API 구현
fix: 로그인 토큰 만료 오류 수정
refactor: PatentService 책임 분리
chore: PR 템플릿 추가
```

<br/>

## 🎯 Project Goal

SKIPA는 특허 관리 담당자가 더 빠르고 근거 있게 의사결정할 수 있도록 돕는 것을 목표로 합니다.

AI는 최종 판단을 대체하는 것이 아니라, 특허 평가에 필요한 정보와 근거를 구조화하여 법무팀과 사업부서의 의사결정을 보조합니다.
