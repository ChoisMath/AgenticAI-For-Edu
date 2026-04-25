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

## 설치 방법

### 방법 1. Claude 데스크톱 앱(Cowork) 사용자

1. 이 저장소를 **Code → Download ZIP**으로 받거나, `git clone`으로 복제합니다.

   ```bash
   git clone https://github.com/<YOUR_USERNAME>/claude-skills-for-teachers.git
   ```

2. 사용하고 싶은 스킬 폴더(예: `reading-material/`)를 통째로 본인의 Claude 스킬 디렉터리로 복사합니다.
   - macOS: `~/Library/Application Support/Claude/skills/`
   - Windows: `%APPDATA%\Claude\skills\`

3. Claude 앱을 재시작하면 새 스킬이 자동으로 인식됩니다.

### 방법 2. Claude Code CLI 사용자

`~/.claude/skills/` 아래에 원하는 스킬 폴더를 복사하면 즉시 사용 가능합니다.

```bash
cp -r reading-material ~/.claude/skills/
```

> **팁**: 다섯 스킬을 모두 한 번에 설치하려면 `cp -r */ ~/.claude/skills/`로 처리할 수 있습니다 (저장소 루트에서 실행).

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
