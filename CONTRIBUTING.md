# Contributing Guide

## 이슈 먼저

작업 전에 반드시 이슈를 먼저 생성\
이슈 없이 바로 PR 올리지 않기

---

## 브랜치 전략

### Prefix 규칙

| prefix    | 용도                             |
| --------- | -------------------------------- |
| `update/` | outdated 내용 수정               |
| `fix/`    | 오탈자, 링크 깨짐 등 사소한 수정 |
| `docs/`   | 새 모듈/콘텐츠 추가              |

### 브랜치명 형식

```
<prefix>/part<N>-module<NN>-<brief-description>
```

예시

```
update/part2-module05-deprecated-api
fix/part1-module02-typo
docs/part5-new-pod-identity-lab
```

### 병렬 작업

서로 다른 모듈이면 동시에 브랜치를 생성 가능\
같은 파일을 건드리는 경우에만 먼저 올라간 PR 머지 후 rebase하고 작업

---

## PR 규칙

- 하나의 PR은 하나의 이슈만 해결
- `fix/` 류 사소한 수정은 리뷰 없이 머지 가능
- `update/`, `docs/` 는 최소 1명 리뷰 후 머지
- PR 제목 형식: `[PART-N] 변경 내용 요약`
