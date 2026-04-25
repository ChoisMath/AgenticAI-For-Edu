# claude-skills-for-teachers

중·고등학교 교사가 수업 자료를 만들 때 곧바로 쓸 수 있는 **Claude Skills 모음**입니다. 다섯 개의 스킬이 수업의 흐름을 따라 서로 짝을 이루도록 설계되었습니다 — 읽히고, 활동하게 하고, 손으로 조작하게 하고, 자기 사건으로 만들고, 마지막에 한 번 더 점검하는 흐름입니다.

> 책임자: **SSamVibe**
> 라이선스: [MIT](./LICENSE)

---

## 어떤 스킬이 들어 있나요?

| 스킬 | 한 줄 설명 | 호출 시점 |
|---|---|---|
| [`reading-material`](./reading-material) | 학생을 텍스트 앞에 멈춰 세우는 사고 유발 읽기 자료 | 단원 도입부, 본문 학습용 글 |
| [`activity-sheet`](./activity-sheet) | '예상–확인–설명–재해석' 4단 구조의 종이 활동지 | 차시 활동, 워크시트 |
| [`interactive-visualizer`](./interactive-visualizer) | 슬라이더·그래프로 학생이 직접 조작하는 학습 도구 (Claude Artifact) | 개념 체득, 탐구 도구 |
| [`case-based-problem`](./case-based-problem) | 학생을 의사결정자의 자리에 세우는 사례·상황 제시문 | 단원 진입점 또는 통합·마무리 |
| [`material-validator`](./material-validator) | 사실확인·시의성·편향·저작권·학생적합성 5명 비평가 점검 | **자료 배포 직전(마지막 게이트)** |

각 폴더 안의 `SKILL.md`가 해당 스킬의 정식 정의 파일입니다. `resources/`에는 작성 기준이 되는 자료가, `subagents/`에는 비평가 모드 정의가 들어 있습니다.

---

## 스킬 다섯 개의 흐름

```
[reading-material]           ──▶ 단원 도입부에서 학생을 멈춰 세움
        │
        ▼
[activity-sheet]             ──▶ 사고 흐름을 종이 위에 시각화
        │
        ▼
[interactive-visualizer]     ──▶ 손으로 조작하며 개념 체득
        │
        ▼
[case-based-problem]         ──▶ 자기 가치관으로 결정 내림
        │
        ▼
[material-validator]         ──▶ 배포 직전, 다섯 비평가가 마지막 점검
```

이 순서는 강제가 아니라 권장입니다. 단원 성격에 따라 한두 개만 골라 써도 되고, 순서를 뒤집어도 됩니다. 단 **`material-validator`만은 학생 배포 직전에 항상 호출**하는 것을 권장합니다.

---

## Claude Project 지침

스킬 5개를 한 Project에 묶어 쓸 때 사용할 **Project Instructions** 텍스트를 별도 파일로 제공합니다.

→ **[claude-project-instructions.md 보기/복사](https://github.com/ChoisMath/AgenticAI-For-Edu/blob/main/claude-project-instructions.md)**

페이지 우측 상단의 **복사 아이콘(📋)** 한 번이면 전체 내용이 클립보드에 들어갑니다. claude.ai에서 새 Project를 만들고 **Project Instructions** 영역에 그대로 붙여넣으세요.

---

## 설치 방법

> 어떤 방식이든 항상 **[최신 릴리즈 페이지](https://github.com/ChoisMath/AgenticAI-For-Edu/releases/latest)** 에서 다운로드하세요. 책 개정 시 이 링크는 자동으로 최신 버전을 가리킵니다.

### 방법 1. claude.ai 웹 사용자 (가장 일반적)

1. **[최신 릴리즈](https://github.com/ChoisMath/AgenticAI-For-Edu/releases/latest)** 에서 원하는 스킬 ZIP을 클릭해 다운로드합니다.
   - 한 개만 필요하면: `reading-material.zip` 같이 개별 파일
   - 다섯 개를 한꺼번에 받고 싶다면: `claude-skills-for-teachers-all.zip`
2. claude.ai 접속 → **설정(Settings) → Capabilities → Skills → Upload skill**.
3. 다운받은 ZIP을 그대로 업로드합니다. **압축 해제 불필요.**

### 방법 2. Claude 데스크톱 앱(Cowork) 사용자

1. 위 릴리즈 페이지에서 원하는 스킬 ZIP을 받아 압축을 풉니다.
2. 풀어낸 스킬 폴더(예: `reading-material/`)를 본인의 Claude 스킬 디렉터리에 복사합니다.
   - macOS: `~/Library/Application Support/Claude/skills/`
   - Windows: `%APPDATA%\Claude\skills\`
3. Claude 앱을 재시작하면 새 스킬이 자동으로 인식됩니다.

### 방법 3. Claude Code CLI 사용자

`~/.claude/skills/` 아래에 원하는 스킬 폴더를 복사하면 즉시 사용 가능합니다.

```bash
git clone https://github.com/ChoisMath/AgenticAI-For-Edu.git
cp -r AgenticAI-For-Edu/reading-material ~/.claude/skills/
```

> **팁**: 다섯 스킬을 한 번에 설치하려면 저장소 루트에서 `cp -r */ ~/.claude/skills/`.

---

## 업데이트 받기

스킬이 개정되면 [Releases 페이지](https://github.com/ChoisMath/AgenticAI-For-Edu/releases)에 새 버전이 올라옵니다. 같은 방법으로 다시 다운로드하여 업로드/복사하면 기존 스킬을 덮어씁니다. 자동 업데이트는 되지 않으므로, 책의 새 판이 나오거나 공지가 있을 때 다시 받아주세요.

---

## 스킬 호출 예시

스킬이 설치되면 Claude에게 자연스럽게 부탁하기만 하면 됩니다.

```
"<대수> 지수함수의 활용 단원 도입부 읽기 자료 만들어 줘. 고2, 800자."
→ reading-material 자동 호출

"방금 그 자료에 맞는 활동지 만들어 줘. A4 한 장, 1차시."
→ activity-sheet 자동 호출

"학생이 슬라이더로 직접 조작할 수 있는 인터랙티브 도구로 만들어 줘."
→ interactive-visualizer 자동 호출

"학생이 자기 결정을 내려야 하는 사례 기반 문제도 같이 만들자."
→ case-based-problem 자동 호출

"이 자료들 학생에게 나누기 전에 점검해 줘."
→ material-validator 자동 호출 (다섯 비평가 동시 가동)
```

---

## 폴더 구조

```
claude-skills-for-teachers/
├── README.md
├── LICENSE
├── .gitignore
│
├── reading-material/
│   ├── SKILL.md
│   ├── resources/
│   │   ├── 3가지_조건.md
│   │   └── 4가지_문제_진단.md
│   └── subagents/
│       └── 비평가.md
│
├── activity-sheet/
│   ├── SKILL.md
│   ├── resources/
│   │   ├── 4단_구조_설계.md
│   │   └── 세_층위_분포.md
│   └── subagents/
│       └── 비평가.md
│
├── interactive-visualizer/
│   ├── SKILL.md
│   ├── resources/
│   │   ├── Mayer_5원리.md
│   │   └── 좋은_바이브코딩_프롬프트의_4요소.md
│   └── subagents/
│       └── 비평가.md
│
├── case-based-problem/
│   ├── SKILL.md
│   ├── resources/
│   │   ├── 사례_4가지_조건.md
│   │   └── 사례_표준_6원칙.md
│   └── subagents/
│       └── 비평가.md
│
└── material-validator/
    ├── SKILL.md
    ├── resources/
    │   ├── 5분_점검_5항목.md
    │   └── 위험_신호_진단표.md
    └── subagents/
        ├── 사실확인_비평가.md
        ├── 시의성_비평가.md
        ├── 저작권_비평가.md
        ├── 편향_비평가.md
        └── 학생적합성_비평가.md
```

---

## 기여 / 피드백

수업에 쓰시면서 발견한 개선점·오류·아이디어가 있다면 GitHub Issues 또는 Pull Request로 보내주세요. 같은 학교 교사뿐 아니라 다른 학교·다른 교과의 사례가 큰 도움이 됩니다.

---

## 라이선스

MIT License — 자유롭게 다운로드, 수정, 수업 활용, 재배포가 가능합니다. 자세한 내용은 [LICENSE](./LICENSE)를 참고해 주세요.
