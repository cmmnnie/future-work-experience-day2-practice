# 충돌 연습장

> 이 파일은 **일부러 충돌을 만들어 보라고** 준비한 파일입니다.
> 여기서 실수해도 아무 일도 일어나지 않습니다. 마음껏 망가뜨리세요.
> 해결 방법: [`../cheatsheet/conflict-howto.md`](../cheatsheet/conflict-howto.md)

---

## 연습 순서

**① GitHub 웹에서 고치기**
이 파일을 GitHub 웹에서 열고 연필(✏️) 아이콘 → 아래 `[여기]` 줄을 **A**로 고쳐 **Commit changes**

**② 내 컴퓨터에서 다르게 고치기**
`git pull` 을 **하지 않은 채로**, 같은 줄을 **B**로 고치고

```bash
git add sandbox/CONFLICT.md
git commit -m "docs: 오늘의 한 문장 작성"
git push
```

**③ 거절 확인**
`! [rejected] main -> main (non-fast-forward)` → 정상입니다.

**④ 받아오고 해결하기**

```bash
git pull --no-rebase origin main
```

`CONFLICT (content)` 가 나오면 마커 세 줄을 지우고 남길 내용만 남긴 뒤

```bash
git add sandbox/CONFLICT.md
git commit -m "fix: 충돌 해결"
git push
```

---

## 고칠 줄 — 여기입니다

오늘의 한 문장: [여기]

---

> 다 하셨으면 위 줄을 원래대로 `[여기]` 로 돌려놓아도 되고, 그대로 두셔도 됩니다.
> **충돌을 교실에서 미리 겪어 본 사람은 실무에서 당황하지 않습니다.**
