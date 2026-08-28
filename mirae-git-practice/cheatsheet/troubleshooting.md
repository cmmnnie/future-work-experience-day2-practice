# 막혔을 때 — 자주 나오는 문제

> **빨간 글씨 = 실패가 아닙니다.** Git과 브라우저는 대부분 "다음에 무엇을 하라"까지 함께 알려줍니다.
> 메시지의 **마지막 줄부터** 읽어보세요.

---

## Git · GitHub

| 이런 메시지가 보이면 | 왜 그런가 | 이렇게 하세요 |
| --- | --- | --- |
| `git: command not found` | 설치 후 터미널이 인식 못 함 | 터미널을 **완전히 껐다가** 다시 열기 |
| push 시 인증 실패 (403) | 계정·권한·저장된 로그인 정보 | 브라우저 재로그인 → 안 되면 손 들기 |
| `! [rejected] non-fast-forward` | 원격에 내게 없는 커밋이 있음 | `git pull --no-rebase origin main` → 충돌 해결 → push |
| 까만 화면(Vim)이 열림 | `-m` 옵션을 빠뜨림 | **Esc** → `:q!` → Enter 로 탈출 후 재시도 |
| `fatal: not a git repository` | 저장소 폴더 밖에 있음 | `cd my-first-repo` 로 폴더 안으로 이동 |
| `no upstream branch` | 새 브랜치 첫 push | `git push -u origin 브랜치명` |
| `git switch` 가 없는 명령이라고 나옴 | Git 구버전 | `git checkout -b 브랜치명` 으로 대체 |
| 한글 파일명이 깨져 보임 | quotepath 기본 설정 | `git config --global core.quotepath false` |
| main에서 파일을 만들어버림 | 브랜치 이동 전 작업 | `git stash` → `git switch -c 브랜치명` → `git stash pop` |
| PR 버튼(Compare & pull request)이 안 보임 | push 후 시간 경과 | 저장소 상단 **branches** → 해당 브랜치 → New pull request |

---

## Fork 관련

| 증상 | 해결 |
| --- | --- |
| Fork 버튼이 안 보임 | GitHub 로그인 상태를 확인하세요. 로그아웃 상태에서는 안 보입니다 |
| PR의 base가 원본 저장소로 잡힘 | PR 화면 위쪽 `base repository`를 **내 계정**으로 변경 |
| 실수로 원본에 PR을 보냄 | 그냥 **Close pull request**. 아무 문제 없습니다 |
| Fork가 원본보다 뒤처짐 | 저장소 상단 **Sync fork** → **Update branch** |

---

## 7교시 · 날씨 미니앱

| 증상 | 원인 | 해결 |
| --- | --- | --- |
| 파일을 열면 코드가 그대로 보임 | `.txt` 로 저장됨 | 파일명 `weather.html` · 형식 **"모든 파일"** 로 재저장 |
| 버튼을 눌러도 반응 없음 | 템플릿 일부만 복사됨 | 템플릿 **전체**를 다시 복사해 저장 → 새로고침 |
| 한글로 "서울" 입력 시 404 | 도시명은 영문 기준 | `Seoul` · 동명 도시는 `Seoul,KR` 형식 |
| 온도가 300도로 나옴 | 단위 지정 누락 (켈빈이 기본) | 요청에 `units=metric` 포함 여부 확인 |
| 응답 설명이 영어로 나옴 | 언어 지정 누락 | `lang=kr` 확인 — 있어도 일부 항목은 영문입니다 |
| 방금 발급한 키인데 401 | 키 활성화 지연 | 프록시 또는 mock 경로로 진행, 본인 키는 쉬는 시간에 재시도 |
| 아무것도 안 뜨고 조용함 | JavaScript 오류 | 브라우저에서 **F12** → Console 탭 확인 |

---

## 오류의 종류부터 구분하기

모든 오류를 같은 순서로 읽지 않습니다. **종류를 먼저 구분**하면 절반은 해결됩니다.

| 오류 종류 | 사례 | 가장 먼저 볼 것 |
| --- | --- | --- |
| 언어 · 런타임 | Python `NameError` | 마지막 요약 줄 + 내 코드의 파일·줄 번호 |
| HTTP · API | `401 Invalid API key` | 상태 코드 + 응답 본문 + 인증 파라미터 |
| Git | `non-fast-forward` | 로컬·원격 브랜치와 커밋 차이 |

---

## 질문할 때 — 네 줄이면 됩니다

```
① 하려던 것 :
② 실제 결과 · 오류 전문 :
③ 이미 시도한 것 :
④ 현재 가설 · 원하는 도움 :
```

붙여넣기 전에 **API 키·비밀번호·개인정보가 섞여 있지 않은지** 확인하세요.
