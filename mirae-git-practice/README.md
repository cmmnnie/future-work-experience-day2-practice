# 미래내일 일경험 · IT 2일차 실습 재료 저장소

2일차 사전직무교육(GitHub · 설계 · API · 알고리즘)에서 쓰는 **템플릿 · 워크시트 · 치트시트**가 들어 있습니다.
수업 중 필요한 파일을 여기서 열어 복사해 쓰시면 됩니다.

---

## ⚠️ 먼저 알아두실 것

**이 저장소는 재료 창고입니다. 여러분이 실습으로 만드는 저장소는 따로입니다.**

| | 이 저장소 (`mirae-git-practice`) | 내 실습 저장소 (`my-first-repo`) |
| --- | --- | --- |
| 언제 | 지금 Fork 해 둡니다 | 1교시 실습 ①에서 직접 만듭니다 |
| 역할 | 템플릿·워크시트를 **가져다 쓰는 곳** | 커밋·PR·충돌 실습을 **직접 하는 곳** |
| 커밋 | 안 해도 됩니다 | 여기에 오늘의 결과물이 쌓입니다 |

파일을 옮기는 게 아니라 **내용을 복사해서** 내 실습 저장소에 새로 만드는 방식입니다.

---

## 시작하기 (3분)

**1. Fork** — 이 페이지 오른쪽 위 **Fork** 버튼 → **Create fork**
   내 계정에 사본이 생깁니다. 주소가 `github.com/내아이디/mirae-git-practice`로 바뀌면 성공입니다.

**2. Clone** — 초록색 **Code** 버튼에서 HTTPS 주소를 복사한 뒤 터미널에서

```bash
git clone https://github.com/내아이디/mirae-git-practice.git
cd mirae-git-practice
```

**3. 폴더를 열어두기** — 수업 내내 이 폴더를 탐색기(Finder)에 띄워 두세요.

> Fork가 안 보이거나 막히면 그냥 **Code → Download ZIP** 으로 받아도 수업 진행에 지장 없습니다.

---

## 무엇이 들어 있나

| 경로 | 무엇 | 쓰는 시점 |
| --- | --- | --- |
| [`cheatsheet/git-commands.md`](cheatsheet/git-commands.md) | 복붙용 Git 명령어 모음 | 1~2교시 · 6교시 |
| [`cheatsheet/conflict-howto.md`](cheatsheet/conflict-howto.md) | 충돌 해결 3단계 | 2교시 실습 ③ |
| [`cheatsheet/troubleshooting.md`](cheatsheet/troubleshooting.md) | 막혔을 때 보는 표 | 하루 종일 |
| [`templates/DESIGN.md`](templates/DESIGN.md) | 미니 설계서 템플릿 | 3교시 실습 ④ |
| [`worksheets/05-error-diagnosis.md`](worksheets/05-error-diagnosis.md) | 오류 진단 워크시트 | 5교시 실습 ⑤ |
| [`templates/weather.html`](templates/weather.html) | 날씨 조회 미니앱 템플릿 | 7교시 실습 ⑦ |
| [`worksheets/08-two-week-card.md`](worksheets/08-two-week-card.md) | 2주 실행 카드 | 8교시 |
| [`sandbox/CONFLICT.md`](sandbox/CONFLICT.md) | 충돌을 안전하게 연습할 파일 | 2교시 (선택) |

---

## 교시별 사용법

### 1~2교시 · Git과 GitHub

`cheatsheet/git-commands.md`를 열어두고 명령어를 복사해 씁니다.
실습 ①에서 만드는 저장소는 **여러분이 직접 새로 만드는** `my-first-repo`입니다.

### 3교시 · 미니 설계 워크숍 (실습 ④)

`templates/DESIGN.md`를 열어 **내용을 전부 복사** → 내 `my-first-repo` 폴더 안에 `DESIGN.md`로 저장 → 빈칸을 채웁니다.

### 5교시 · 오류 진단 (실습 ⑤)

`worksheets/05-error-diagnosis.md`를 열어 표를 채웁니다. 커밋하지 않아도 됩니다.

### 6교시 · 브랜치 + AI 커밋 메시지 (실습 ⑥)

3교시에 만든 `DESIGN.md`를 `my-first-repo`에서 브랜치로 커밋합니다. 명령어는 치트시트에 있습니다.

### 7교시 · 날씨 조회 미니앱 (실습 ⑦)

`templates/weather.html`을 **전체 복사** → `my-first-repo` 폴더에 `weather.html`로 저장 → 브라우저에서 엽니다.
기본은 `USE_MOCK = true`라 인터넷이나 API 키 없이도 화면이 뜹니다.

### 8교시 · 2주 실행 카드

`worksheets/08-two-week-card.md`를 채워 오늘 가져갑니다.

---

## ⚠️ Pull Request를 만들 때 꼭 확인하세요

Fork한 저장소에서 PR을 만들면 GitHub이 **기본으로 원본 저장소(`cooldevsmart/mirae-git-practice`)를 대상으로 잡습니다.**

PR 화면 맨 위의 이런 줄을 반드시 확인하세요.

```
base repository: cooldevsmart/mirae-git-practice  ←  이러면 잘못된 것
base repository: 내아이디/mirae-git-practice      ←  이렇게 바꿔야 합니다
```

`base repository`를 눌러 **내 계정**으로 바꾼 뒤 PR을 만드세요.
실수로 원본에 PR을 보내셨다면 그냥 **Close pull request**를 누르면 됩니다. 아무 문제 없습니다.

---

## 보안 — 오늘의 규칙 두 가지

1. **API 키·비밀번호를 커밋하지 않습니다.** `weather.html`에 실제 키를 넣지 마세요. 수업은 프록시 또는 mock으로 진행합니다.
2. **에러 메시지를 검색창이나 AI에 붙여넣기 전에** 키·개인정보가 섞여 있지 않은지 확인합니다.

실수로 키를 커밋했다면 지우는 것만으로는 이력에 남습니다. **즉시 해당 키를 폐기하고 재발급**하세요.

---

## 막혔을 때

1. [`cheatsheet/troubleshooting.md`](cheatsheet/troubleshooting.md)를 먼저 확인
2. 그래도 안 되면 손 들기 (오프라인) / 채팅에 `❓` (온라인)
3. 질문할 때는 **① 하려던 것 ② 실제 결과·오류 전문 ③ 시도한 것 ④ 현재 가설** 네 줄로

---

_미래내일 일경험 IT 직무 사전직무교육 2일차 · 강사 임대건_
