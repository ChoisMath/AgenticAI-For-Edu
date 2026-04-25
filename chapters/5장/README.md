# 5장. _(여기에 장 제목을 적어주세요)_

> 이 장의 한 줄 설명을 적습니다.

---

## 이 장에 포함된 자료

### 📋 Claude Project 지침

스킬 5개를 한 Project에 묶어 사용할 때 붙여 쓰는 시스템 프롬프트입니다.

→ **[claude-project-instructions.md 보기/복사](./claude-project-instructions.md)**

페이지 우측 상단 복사 아이콘(📋)으로 전체 내용을 클립보드에 담아 claude.ai Project에 붙여넣으세요.

### 🛠️ Claude Skills (5개)

| 스킬 | 한 줄 설명 | 호출 시점 |
|---|---|---|
| [`reading-material`](./skills/reading-material) | 학생을 텍스트 앞에 멈춰 세우는 사고 유발 읽기 자료 | 단원 도입부, 본문 학습용 글 |
| [`activity-sheet`](./skills/activity-sheet) | '예상–확인–설명–재해석' 4단 구조의 종이 활동지 | 차시 활동, 워크시트 |
| [`interactive-visualizer`](./skills/interactive-visualizer) | 슬라이더·그래프로 학생이 직접 조작하는 학습 도구 (Claude Artifact) | 개념 체득, 탐구 도구 |
| [`case-based-problem`](./skills/case-based-problem) | 학생을 의사결정자의 자리에 세우는 사례·상황 제시문 | 단원 진입점 또는 통합·마무리 |
| [`material-validator`](./skills/material-validator) | 사실확인·시의성·편향·저작권·학생적합성 5명 비평가 점검 | **자료 배포 직전(마지막 게이트)** |

각 스킬 ZIP 다운로드는 [최신 릴리즈 페이지](https://github.com/ChoisMath/AgenticAI-For-Edu/releases/latest)에서 `5장-<스킬이름>.zip` 형식으로 제공됩니다.

---

## 다섯 스킬의 흐름

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
