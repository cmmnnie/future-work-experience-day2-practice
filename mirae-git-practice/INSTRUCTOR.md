# 강사용 운영 노트

> 수강생은 읽지 않아도 되는 파일입니다. 저장소 운영과 당일 진행 방법을 정리했습니다.

---

## 이 저장소의 역할

**재료 창고입니다.** 수강생이 실습으로 만드는 저장소는 교안 실습 ①의 `my-first-repo` 이고,
이 저장소는 템플릿·워크시트·치트시트를 **가져다 쓰는 곳**입니다.

교안 실습 ①(저장소 생성 → clone → 첫 커밋)은 **수정 없이 그대로** 진행합니다.

---

## D-1 준비

- [ ] 저장소가 **Public** 인지 확인 (Private 이면 수강생이 Fork 할 수 없습니다)
- [ ] Settings → General → Features 에서 **Issues 끄기** (수강생 오폭 방지, 선택)
- [ ] `templates/weather.html` 을 브라우저로 열어 mock 모드 동작 확인
- [ ] 프록시를 준비했다면 `EDU_ENDPOINT` 주소를 워크북에 반영
- [ ] Fork 링크를 짧은 주소로 만들어 두기 (수업 중 채팅으로 배포)

---

## 당일 진행

### 오프닝 (실습 환경 체크 시간)

Fork를 **이때 미리** 시켜두면 1교시가 매끄럽습니다.

> "지금 링크 하나 보내드릴게요. 오른쪽 위 **Fork** 버튼만 눌러주세요. 3분입니다."

Fork가 안 되는 수강생은 **Code → Download ZIP** 으로 진행해도 수업에 지장 없습니다.

### 교시별 사용 지점

| 교시 | 파일 | 하는 일 |
| --- | --- | --- |
| 1~2 | `cheatsheet/git-commands.md` | 명령어를 여기서 복사 |
| 2 | `cheatsheet/conflict-howto.md`, `sandbox/CONFLICT.md` | 충돌 데모·선택 실습 |
| 3 | `templates/DESIGN.md` | 내용 복사 → `my-first-repo` 에 저장 |
| 5 | `worksheets/05-error-diagnosis.md` | 화면에서 바로 작성 |
| 6 | `cheatsheet/git-commands.md` §4~5 | preflight·브랜치·AI 프롬프트 |
| 7 | `templates/weather.html` | 전체 복사 → `weather.html` 저장 |
| 8 | `worksheets/08-two-week-card.md` | 작성 후 각자 보관 |

---

## 자주 생기는 사고와 대응

**① 수강생이 원본 저장소로 PR을 보냄**
가장 흔한 사고입니다. `.github/pull_request_template.md` 에 경고를 넣어뒀지만 그래도 옵니다.
→ 그냥 **Close** 하면 됩니다. 수업 중에는 "PR 화면 위쪽 base repository를 본인 계정으로" 를 한 번 시연해 주세요.

**② Fork 저장소와 실습 저장소를 헷갈림**
"창고와 작업대" 비유로 한 번 정리해 주면 대부분 해결됩니다.
→ 창고(`mirae-git-practice`)에서 재료를 꺼내, 작업대(`my-first-repo`)에서 만듭니다.

**③ 파일을 옮기려고 시도**
파일 이동이 아니라 **내용 복사**임을 명확히 하세요. 드래그로 옮기면 git 이력이 꼬입니다.

**④ 원본이 업데이트됐는데 Fork가 뒤처짐**
수강생 저장소 상단 **Sync fork → Update branch**. 수업 중엔 거의 필요 없습니다.

---

## 저장소를 고칠 때

수업 자료를 수정하면 **이미 Fork 한 수강생에게는 자동 반영되지 않습니다.**
수업 당일 아침 이후로는 가급적 수정하지 마시고, 꼭 필요하면 채팅으로 별도 공지하세요.

---

## 진행 상황 확인

저장소 상단 **Insights → Forks** 에서 누가 Fork 했는지 볼 수 있습니다.
출석 확인 용도로 쓸 수 있지만, Fork 를 안 한 수강생도 ZIP 경로로 따라올 수 있으니 **필수 조건으로 걸지는 마세요.**

---

## 관련 자료

- 교시별 교안 본문 5건 (정본)
- 수강생용 실습 워크북 — 2일차
- 2일차 교안 PPTX (87장)

> ⚠️ 워크북의 `weather.html` 템플릿이 구버전(API 키 직접 입력)이면
> 이 저장소의 `templates/weather.html`(프록시/mock)로 교체해서 배포하세요.
