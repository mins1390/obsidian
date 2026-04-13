# 10. Literature 폴더

## 목적과 역할

**외부 원천 자료에서 얻은 문헌 노트**를 보관하는 폴더입니다.
저자의 생각을 내 언어로 요약하되, 아직 내 해석은 최소화합니다.

## 어떤 노트가 들어가는가

- 책에서 얻은 핵심 내용 요약
- 논문/글/영상/강의 노트
- 팟캐스트, 인터뷰 내용 정리
- 원저자의 주장을 담은 노트

### 예시

- `[책] 아토믹 해빗 - 제임스 클리어.md`
- `[논문] 간헐적 단식 효과 연구.md`
- `[영상] 리처드 파인만의 학습법.md`

## 작업 방식과 규칙

1. **출처 명시 필수**: `source`, `author` Frontmatter 기입
2. **내 언어로 요약**: 단순 복사/붙여넣기 금지
3. **Permanent로 발전**: 가치 있는 내용은 `20. Permanent`에 내 해석 추가
4. **원천과 해석 분리**: Literature = 저자의 생각 / Permanent = 나의 통찰

### Frontmatter 템플릿

```yaml
---
type: literature
status: active
created: YYYY-MM-DD
updated: YYYY-MM-DD
source: "[[출처 제목]]"
author: "저자명"
tags: [literature]
---
```

### Literature → Permanent 흐름

```
외부 자료 읽기
  → Literature 노트 작성 (저자의 생각 요약)
  → 인사이트 발견
  → Permanent 노트 작성 (내 언어로 재구성)
  → Literature 노트에 [[Permanent 링크]] 추가
```
