# ai

코딩 에이전트(Claude Code 등)를 더 잘 쓰기 위한 공부. 남이 만든 방법론을 그대로 들여와 읽고, 내 식으로 고쳐 보면서 배운다.

| 폴더 | 무엇 | 들여온 방식 | 시작 |
|---|---|---|---|
| [`superpowers/`](superpowers/) | [obra/superpowers](https://github.com/obra/superpowers) — 코딩 에이전트용 스킬 14개 + 개발 방법론 (brainstorming → writing-plans → subagent-driven-development, TDD·systematic-debugging·code-review 등). MIT | `git subtree` (squash) | 2026-09-03 |

## superpowers 를 subtree 로 둔 이유

- 파일이 이 저장소 안에 그대로 들어와 있어 **마음대로 고칠 수 있다.** submodule 이면 편집한 커밋을 올릴 곳(원본 push 권한)이 없어 깨진다.
- 원본이 바뀌면 아래 한 줄로 당겨와 내 수정과 합칠 수 있다. fork 를 따로 관리할 필요가 없다.
- 들여올 때 원본 이력은 squash 해서 커밋 하나로 접었다. 들여온 시점의 원본 커밋: `b36e082` (v6.3.0).

```bash
# 원본 최신을 당겨와 내 수정과 합친다 (충돌 나면 손으로 푼다)
git subtree pull --prefix=ai/superpowers https://github.com/obra/superpowers.git main --squash
```

## 알아 둘 것

- `superpowers/CLAUDE.md` 는 **원본의 기여자 지침**이다 (AI 에이전트가 원본에 PR 을 낼 때의 규칙). Claude Code 는 하위 폴더 CLAUDE.md 도 그 폴더를 다룰 때 읽으므로, 이 안에서 작업하면 그 지침이 따라온다. 이 저장소에 두는 목적은 읽고 고쳐 보는 것이지 원본에 PR 을 내는 것이 아니다.
- 폴더에 있다고 플러그인이 켜지는 것은 아니다. 실제로 써 보려면 `/plugin install superpowers@claude-plugins-official` 로 따로 설치한다.
- 라이선스는 MIT — `superpowers/LICENSE` 를 지우지 않는다. 고친 파일은 원본과 다르다는 것을 커밋 메시지에 남긴다.
