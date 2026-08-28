# 복붙용 Git 명령어 모음

> 명령어는 외우지 마세요. 필요할 때 여기서 복사해 쓰면 됩니다.
> 오늘 기억할 리듬은 하나 — **`status`로 확인하고, `add`로 담고, `commit`으로 찍는다.**

---

## 0. 설치 확인 & 최초 설정 (실습 ⓪)

```bash
git --version
```

`git version 2.x.x` 가 나오면 설치 성공입니다.

```bash
git config --global user.name "홍길동"
git config --global user.email "hong@example.com"
git config --list
```

이 이름과 이메일이 앞으로 남기는 **모든 커밋에 서명처럼** 찍힙니다.

한글 파일명이 깨져 보이면 한 번만 실행하세요.

```bash
git config --global core.quotepath false
```

---

## 1. 첫 저장소 & 첫 커밋 (실습 ①)

GitHub에서 **New repository** → 이름 `my-first-repo` → Public → **Add a README file 체크** → Create

```bash
git clone https://github.com/내아이디/my-first-repo.git
cd my-first-repo
```

`README.md`를 편집기로 열어 자기소개 한 줄을 추가하고 저장한 뒤,

```bash
git status
```

`modified: README.md` 가 보이면 저장 성공입니다.

```bash
git add README.md
git status
git commit -m "docs: 자기소개 한 줄 추가"
git log --oneline
```

```bash
git push origin main
```

GitHub 저장소를 새로고침해서 커밋 메시지가 보이면 완료입니다.

---

## 2. 커밋 메시지 컨벤션

| 접두어 | 언제 | 예시 |
| --- | --- | --- |
| `feat:` | 기능 추가 | `feat: 도시 검색 기능 추가` |
| `fix:` | 버그 수정 | `fix: 로그인 실패 시 에러 미표시 수정` |
| `docs:` | 문서 | `docs: README에 자기소개 추가` |

**한 가지 변경 = 한 커밋**이 기본입니다.

---

## 3. 원격 저장소 동기화

```bash
git push origin main          # 올리기 ↑
git pull origin main          # 내리기 ↓
git remote -v                 # 원격 주소 확인
```

> `commit`은 내 컴퓨터에만 기록됩니다. **`push`까지 해야** GitHub에 반영됩니다.

---

## 4. 브랜치 (실습 ⑥)

```bash
git switch -c feature/design-doc     # 만들고 이동
git branch                           # 목록 (* 가 지금 내 위치)
git switch main                      # 본 줄기로 복귀
```

구버전 Git이라 `switch`가 없다고 나오면:

```bash
git checkout -b feature/design-doc
```

### 작업 시작 전 점검 (preflight)

```bash
git status                    # working tree clean 인가?
git branch --show-current     # 지금 main 인가?
git switch main
git pull --ff-only origin main
```

### 변경 확인 → 커밋 → 올리기

```bash
git add DESIGN.md
git diff --cached             # 이번에 무엇이 바뀌었는지 눈으로 확인
git commit -m "docs: 날씨 조회 서비스 설계 문서 추가"
git push -u origin feature/design-doc
```

새 브랜치의 첫 push에는 `-u origin 브랜치명` 이 필요합니다.

### 머지 후 원래대로 되돌리기

```bash
git switch main
git pull --ff-only origin main
git branch -d feature/design-doc     # merge를 마친 경우에만
git status
```

---

## 5. AI에게 커밋 메시지 물어보기 (실습 ⑥)

`git diff --cached`로 변경을 확인한 뒤, **변경 요약만** AI에 전달합니다.
파일 전체나 키가 들어간 코드를 붙여넣지 않습니다.

```
아래 변경 요약을 바탕으로 Conventional Commits 형식의 한국어
커밋 메시지 후보 3개를 제안해줘. 과장하지 말고 실제 변경만.

변경 요약:
- DESIGN.md 추가 — 기능 요구사항 2개, 비기능 요구사항 1개 기록
- wireframe.jpg 추가
```

받은 후보는 그대로 쓰지 말고 **네 가지를 직접 검증**하세요.

1. 실제 diff와 일치하는가
2. `docs` 유형이 맞는가
3. 구현하지 않은 기능을 했다고 과장하지 않았는가
4. 비밀정보가 없는가

---

## 6. 되돌리기

```bash
git restore 파일명             # 아직 add 안 한 변경 되돌리기
git restore --staged 파일명    # add한 것을 장바구니에서 빼기
git revert 커밋해시            # 공유된 커밋을 되돌리는 새 커밋 (안전)
```

> 신입은 `reset`보다 **`revert`부터** 익히세요. `reset`은 이력 자체를 바꿉니다.

---

## 자주 쓰는 것만 다시 (치트시트의 치트시트)

```bash
git status                    # 막히면 언제나 여기부터
git add .
git commit -m "메시지"
git push
git pull
git switch -c 브랜치명
git log --oneline
```
