# 🤝 Contributing Guide

SKIPERS 팀의 GitHub 협업 규칙입니다.

모든 작업은 이슈를 기준으로 진행하며, 아래 흐름을 따릅니다.

```text
이슈 생성 → 브랜치 생성 → 작업 → 커밋 → PR 생성 → 리뷰 → dev 병합
```

---

## 1. 기본 작업 흐름

1. 작업할 내용을 이슈로 등록합니다.
2. 이슈 번호를 기준으로 브랜치를 생성합니다.
3. 작업 후 커밋 컨벤션에 맞춰 커밋합니다.
4. `dev` 브랜치로 Pull Request를 생성합니다.
5. 팀원의 리뷰를 받은 후 병합합니다.
6. 병합 후 작업 브랜치는 삭제합니다.

---

## 2. Branch Strategy

기본 브랜치는 아래와 같이 사용합니다.

| Branch | Description |
|---|---|
| `main` | 최종 배포용 브랜치 |
| `dev` | 개발 통합 브랜치 |
| `feat/*` | 기능 개발 브랜치 |
| `fix/*` | 버그 수정 브랜치 |
| `refactor/*` | 리팩토링 브랜치 |
| `chore/*` | 기타 작업 브랜치 |

모든 작업 브랜치는 `dev` 브랜치에서 생성합니다.

---

## 3. Issue Template 사용 기준

이슈는 작업 성격에 맞는 템플릿을 선택해 작성합니다.

| Issue Template | 사용 상황 | Label |
|---|---|---|
| 기능 제안 | 새로운 기능 추가 또는 기존 기능 개선 | `✨ feature` |
| 버그 리포트 | 오류, 예외, 예상과 다른 동작 수정 | `🐛 bug` |
| 리팩토링 | 기능 변경 없이 코드 구조나 품질 개선 | `♻️ refactor` |
| 일반 작업 | 문서 작성, 설정 변경, 환경 구성 등 기타 작업 | `🔧 chore` |

문서 작업이나 인프라 작업처럼 성격이 명확한 경우, 기본 라벨과 함께 보조 라벨을 추가할 수 있습니다.

| Label | 사용 상황 |
|---|---|
| `📝 docs` | README, API 문서, 가이드 등 문서 작업 |
| `⚙️ infra` | 배포, CI/CD, Docker, 서버, 환경 설정 관련 작업 |


---

## 4. Issue별 Branch Naming Rule

브랜치명은 아래 형식을 따릅니다.

```text
{type}/{issue-number}-{short-description}
```

브랜치명은 영어 소문자와 하이픈을 사용합니다.

### 4.1 기능 제안

새로운 기능 추가 또는 기존 기능 개선 작업에 사용합니다.

```text
feat/{issue-number}-{short-description}
```

예시:

```text
feat/12-patent-search
feat/15-report-generation
```

### 4.2 버그 리포트

오류, 예외, 예상과 다른 동작을 수정하는 작업에 사용합니다.

```text
fix/{issue-number}-{short-description}
```

예시:

```text
fix/21-login-token-error
fix/24-report-api-error
```

### 4.3 리팩토링

기능 변경 없이 코드 구조, 품질, 유지보수성을 개선하는 작업에 사용합니다.

```text
refactor/{issue-number}-{short-description}
```

예시:

```text
refactor/30-patent-service
refactor/33-ai-client-structure
```

### 4.4 일반 작업

문서 작성, 설정 변경, 환경 구성, 템플릿 추가 등 일반 작업에 사용합니다.

```text
chore/{issue-number}-{short-description}
```

예시:

```text
chore/40-update-readme
chore/42-add-issue-template
```

---

## 5. Pull Request 작성 규칙

PR은 작업이 완료된 후 `dev` 브랜치로 생성합니다.

```text
작업 브랜치 → dev
```

예시:

```text
feat/12-patent-search → dev
```

PR 작성 시 다음 내용을 포함합니다.

- PR 개요
- 관련 이슈 번호
- 작업 내용
- 리뷰 요청 사항
- 특이 사항
- 참고 자료

관련 이슈는 아래와 같이 연결합니다.

```md
close #12
```

PR이 병합되면 연결된 이슈가 자동으로 닫힙니다.

관련 이슈가 없다면 `close #` 줄은 삭제합니다.

---

## 6. Issue별 PR 제목 규칙

PR 제목은 아래 형식을 따릅니다.

```text
[Type] 작업 내용
```

### 6.1 기능 제안

기능 추가 또는 개선 작업의 PR 제목은 `[Feat]`를 사용합니다.

```text
[Feat] 특허 목록 조회 기능 구현
```

### 6.2 버그 리포트

버그 수정 작업의 PR 제목은 `[Fix]`를 사용합니다.

```text
[Fix] 로그인 토큰 만료 오류 수정
```

버그 이슈 제목은 `[Bug]`를 사용하지만, PR 제목은 실제 수정 작업을 의미하는 `[Fix]`를 사용합니다.

### 6.3 리팩토링

리팩토링 작업의 PR 제목은 `[Refactor]`를 사용합니다.

```text
[Refactor] 특허 평가 서비스 구조 개선
```

### 6.4 일반 작업

문서 작성, 설정 변경, 환경 구성 등 일반 작업의 PR 제목은 `[Chore]`를 사용합니다.

```text
[Chore] GitHub 이슈 템플릿 추가
```

---

## 7. Commit Convention

커밋 메시지는 아래 형식을 따릅니다.

```text
type: 작업 내용
```

예시:

```text
feat: 특허 목록 조회 API 구현
fix: 로그인 토큰 만료 오류 수정
refactor: 특허 평가 서비스 구조 개선
chore: GitHub 이슈 템플릿 추가
```

### 7.1 Commit Type

| Type | Description |
|---|---|
| `feat` | 새로운 기능 추가 또는 기존 기능 개선 |
| `fix` | 버그 수정 |
| `refactor` | 기능 변경 없는 코드 구조 개선 |
| `chore` | 설정 변경, 환경 구성, 패키지 관리 등 기타 작업 |
| `docs` | 문서 작성 또는 수정 |
| `style` | 코드 포맷팅, 공백, 세미콜론 등 코드 의미에 영향이 없는 수정 |
| `test` | 테스트 코드 추가 또는 수정 |
| `perf` | 성능 개선 |

### 7.2 Commit Message 예시

```text
feat: 특허 상세 조회 API 구현
feat: 유사 특허 분석 결과 화면 구현
fix: 보고서 생성 요청 실패 오류 수정
refactor: PatentService 책임 분리
chore: PR 템플릿 추가
docs: README 프로젝트 설명 추가
test: 특허 목록 조회 테스트 추가
```

---

## 8. Issue, Branch, PR, Commit 연결 예시

### 8.1 기능 개발 예시

| 항목 | 예시 |
|---|---|
| Issue 제목 | `[Feat] 특허 목록 조회 기능 구현` |
| Branch | `feat/12-patent-list` |
| PR 제목 | `[Feat] 특허 목록 조회 기능 구현` |
| Commit | `feat: 특허 목록 조회 API 구현` |

### 8.2 버그 수정 예시

| 항목 | 예시 |
|---|---|
| Issue 제목 | `[Bug] 보고서 생성 오류` |
| Branch | `fix/21-report-generation-error` |
| PR 제목 | `[Fix] 보고서 생성 오류 수정` |
| Commit | `fix: 보고서 생성 실패 오류 수정` |

### 8.3 리팩토링 예시

| 항목 | 예시 |
|---|---|
| Issue 제목 | `[Refactor] 특허 평가 서비스 구조 개선` |
| Branch | `refactor/30-patent-service` |
| PR 제목 | `[Refactor] 특허 평가 서비스 구조 개선` |
| Commit | `refactor: 특허 평가 로직 책임 분리` |

### 8.4 일반 작업 예시

| 항목 | 예시 |
|---|---|
| Issue 제목 | `[Chore] GitHub 템플릿 추가` |
| Branch | `chore/40-github-template` |
| PR 제목 | `[Chore] GitHub 템플릿 추가` |
| Commit | `chore: 이슈 및 PR 템플릿 추가` |

---

## 9. PR Review Rule

PR 리뷰 시 아래 내용을 확인합니다.

- 작업 내용이 이슈 목적에 맞는지 확인합니다.
- 코드가 이해하기 쉬운 구조인지 확인합니다.
- 불필요한 코드, 주석, 로그가 남아 있지 않은지 확인합니다.
- 관련 기능이 정상 동작하는지 확인합니다.
- API, DB, 환경 변수 변경 사항이 있다면 PR에 명시되었는지 확인합니다.

리뷰어가 수정이 필요하다고 판단하면 코멘트를 남기고, 작성자는 수정 후 다시 리뷰를 요청합니다.

---

## 10. Merge Rule

PR은 리뷰가 완료된 후 `dev` 브랜치에 병합합니다.

병합 전 아래 사항을 확인합니다.

- 관련 이슈가 연결되어 있는지 확인합니다.
- 충돌이 없는지 확인합니다.
- 빌드 또는 실행에 문제가 없는지 확인합니다.
- PR 템플릿이 충분히 작성되어 있는지 확인합니다.

병합 후 작업 브랜치는 삭제합니다.

---

## 11. Naming Rule

파일명, 브랜치명, 커밋 타입은 영어 소문자 사용을 권장합니다.

### 11.1 Branch

```text
feat/12-patent-search
fix/21-login-error
refactor/30-report-service
chore/40-update-readme
```

### 11.2 Commit

```text
feat: 특허 검색 기능 구현
fix: 로그인 오류 수정
```

---

## 12. 기타 규칙

- 하나의 PR에는 하나의 이슈만 연결하는 것을 권장합니다.
- 하나의 PR에 너무 많은 변경 사항을 포함하지 않습니다.
- API 명세, 환경 변수, DB 스키마가 변경되는 경우 PR의 특이 사항에 반드시 작성합니다.
- UI 변경이 있는 경우 PR에 화면 캡처를 첨부합니다.
- 팀원이 이해하기 어려운 구현이 있다면 PR 설명이나 코드 주석으로 보완합니다.
