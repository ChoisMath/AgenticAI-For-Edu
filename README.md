# AgenticAI-For-Edu

중·고등학교 교사를 위한 **AgenticAI 활용 가이드 (총 17장)** 의 코드/자료 저장소입니다. 각 장에서 실제로 사용하는 Claude Skill, Project 지침, 보조 자료가 장별 폴더에 들어 있습니다.

> 책임자: **SSamVibe**
> 라이선스: [MIT](./LICENSE)

---

## 장별 자료

📚 **[전체 17장 색인 보기](./chapters/README.md)**

| 장 | 제목 | 폴더 | 상태 |
|---|---|---|---|
| 5장 | 교수학습자료 개발 실전 | [`chapters/5장/`](./chapters/5장) | ✅ 공개 (5개 스킬 + Project 지침) |
| 1~4장 | (제목 등록됨) | [색인 참고](./chapters/README.md) | 📝 준비 중 |
| 6~17장 | (미정) | — | 준비 중 |

새 장이 공개될 때마다 위 색인이 갱신됩니다.

---

## 자료 받는 방법 (공통)

저장소의 자료는 두 종류로 제공됩니다.

### A. Claude Skill (`.zip`)

claude.ai / 데스크톱 앱 / Claude Code 어디서나 쓸 수 있는 스킬 패키지입니다.

1. **[최신 릴리즈 페이지](https://github.com/ChoisMath/AgenticAI-For-Edu/releases/latest)** 접속
2. 원하는 ZIP 다운로드 — 파일명은 `<장번호>장-<스킬이름>.zip` 형식 (예: `5장-reading-material.zip`)
3. 사용 환경에 맞춰 설치:
   - **claude.ai 웹**: 설정 → Capabilities → Skills → Upload skill에 ZIP 그대로 업로드
   - **Claude 데스크톱(Cowork)**: ZIP 풀어 폴더를 `~/Library/Application Support/Claude/skills/` (macOS) 또는 `%APPDATA%\Claude\skills\` (Windows) 로 복사 → 앱 재시작
   - **Claude Code CLI**: ZIP 풀어 폴더를 `~/.claude/skills/` 로 복사

### B. Claude Project 지침 (`.md`)

Project Instructions 영역에 붙여 쓰는 시스템 프롬프트입니다.

1. 해당 장의 `claude-project-instructions.md` 페이지 접속 (장별 README에 링크)
2. 페이지 우측 상단의 **복사 아이콘(📋)** 클릭 → 전체 내용이 클립보드로 들어감
3. claude.ai 새 Project 생성 → **Project Instructions** 영역에 붙여넣기

> 자료가 개정되면 동일한 절차로 다시 받아 덮어쓰면 됩니다. 자동 업데이트는 되지 않습니다.

---

## 폴더 구조

```
AgenticAI-For-Edu/
├── README.md                              # (이 파일) 책 전체 안내
├── LICENSE
├── .gitattributes
├── .github/workflows/release.yml          # 태그 푸시 시 ZIP 자동 빌드
│
└── chapters/
    ├── README.md                          # 17장 색인
    │
    └── 5장/
        ├── README.md                      # 5장 표지 (제목·개요)
        ├── claude-project-instructions.md # 5장용 Project 지침
        └── skills/
            ├── reading-material/
            ├── activity-sheet/
            ├── interactive-visualizer/
            ├── case-based-problem/
            └── material-validator/
```

새 장은 `chapters/<번호>장/` 폴더를 만들어 같은 패턴으로 추가합니다.

---

## 기여 / 피드백

수업에 쓰시면서 발견한 개선점·오류·아이디어가 있다면 GitHub Issues 또는 Pull Request로 보내주세요. 같은 학교 교사뿐 아니라 다른 학교·다른 교과의 사례가 큰 도움이 됩니다.

---

## 라이선스

MIT License — 자유롭게 다운로드, 수정, 수업 활용, 재배포가 가능합니다. 자세한 내용은 [LICENSE](./LICENSE)를 참고해 주세요.
