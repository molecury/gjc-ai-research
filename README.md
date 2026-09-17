# AI-Assisted Research Log

GJC, Codex, Deep Research를 이용한 연구 과정을 재현 가능한 형태로 기록하기 위한 저장소 템플릿입니다.

핵심은 AI와 나눈 대화를 전부 보관하는 것이 아니라 다음 흐름을 남기는 것입니다.

> 연구 질문 → 가설 → 탐색 방법 → 근거 → 반대 근거 → 판단 → 다음 단계

## 시작하기

1. `research/_template/` 디렉터리를 복사해 날짜와 주제에 맞게 이름을 바꿉니다.
2. 연구를 시작하기 전에 `query.md`를 작성합니다.
3. 조사하면서 `sources.md`와 `findings.md`를 함께 갱신합니다.
4. 세션을 마칠 때 `decisions.md`와 세션 `README.md`를 완성합니다.
5. 코드, 표, 그림 같은 결과물은 해당 세션의 `artifacts/`에 둡니다.
6. 검토가 끝난 단위마다 Git 커밋을 만듭니다.

예시:

```bash
cp -r research/_template research/2026-09-17-cd73-literature-review
git add research/2026-09-17-cd73-literature-review
git commit -m "research: document CD73 literature review"
```

## 디렉터리 구성

```text
research-log-template/
├── README.md                  # 저장소의 목적, 원칙, 전체 사용법
├── GIT_GITHUB_SETUP.md        # Git 설치부터 GitHub 연결까지의 절차
├── RESEARCH_LOG.md            # 모든 연구 세션을 시간순으로 요약한 색인
├── .gitignore                 # 비밀정보, 대용량 및 임시 파일 제외 규칙
├── research/
│   └── _template/
│       ├── README.md          # 세션 개요와 재현 정보
│       ├── query.md           # 질문, 범위, 가설, 검색 계획
│       ├── findings.md        # 주장과 근거를 연결한 조사 결과
│       ├── sources.md         # 출처 목록과 원문 검증 상태
│       ├── decisions.md       # 채택·보류·기각한 판단과 이유
│       └── artifacts/
│           └── README.md      # 코드, 표, 그림 등 산출물 설명
└── prompts/
    └── reusable-prompts.md    # 재사용 가능하도록 정제한 프롬프트
```

## 무엇을 어디에 기록할까?

| 내용 | 파일 |
|---|---|
| 프로젝트 전체 목적과 공개 범위 | 루트 `README.md` |
| 연구 세션의 날짜, 도구, 모델, 상태 | 세션 `README.md` |
| 최초 질문, 가설, 검색어, 포함·제외 기준 | `query.md` |
| 주장, 근거, 반대 근거, 신뢰도 | `findings.md` |
| DOI, URL, 접근일, 원문 확인 여부 | `sources.md` |
| 최종 판단, 보류 사항, 판단 책임자 | `decisions.md` |
| 생성한 코드, 데이터 요약, 그림과 표 | `artifacts/` |
| 여러 연구에서 다시 쓸 프롬프트 | `prompts/reusable-prompts.md` |
| 전체 연구 진행 이력 | `RESEARCH_LOG.md` |

## AI 사용 원칙

- AI가 생성한 주장은 원문을 확인하기 전까지 잠정적인 것으로 취급합니다.
- AI가 수행한 일과 연구자가 검증·결정한 일을 구분합니다.
- 모델 이름, 도구 버전, 조사 날짜를 가능한 범위에서 기록합니다.
- 프롬프트에 토큰, 비밀번호, 개인 정보, 비공개 원문을 넣거나 커밋하지 않습니다.
- 논문 전문과 라이선스가 불분명한 자료 대신 서지정보, 요약, 링크를 기록합니다.
- 결과가 나오지 않은 검색과 기각한 가설도 간단히 남깁니다.

## 권장 커밋 메시지

```text
research: define initial question about X
research: add search strategy for X
evidence: add sources supporting hypothesis A
evidence: document conflicting evidence for A
decision: reject hypothesis B
research: summarize deep-research session
```

