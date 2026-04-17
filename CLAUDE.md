# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

이 저장소는 **Obsidian vault**입니다. **Zettelkasten(ZK)**과 **PARA** 시스템을 결합하여 운영됩니다.

## 핵심 원칙

1. **ZK ↔ PARA 명확 분리**: `5. Zettelkasten/`은 시간 독립적 영구 지식, `1. Projects/` / `2. Areas/`는 시간 제약적 실행
2. **참조 우선 원칙**: 복사 금지 — 항상 `[[링크]]` / `![[임베드]]` / `[[블록참조#^id]]` 사용
3. **One Idea per Permanent Note**: 퍼머넌트 노트는 하나의 주장/개념만, 최소 2개 기존 노트와 연결
4. **ZK는 영구 보관**: ZK 노트는 Archive 이동/삭제 금지, PARA 활용 시 복제본만 생성

## 저장소 구조

```
보관/
├── 0. Docs/               # 운영 규칙, 정책 문서 (평면 구조)
├── 1. Projects/           # PARA: 기한 있는 프로젝트
├── 2. Areas/              # PARA: 지속적 관리 영역
├── 3. Resources/          # PARA: 참고 자료
├── 4. Archive/            # PARA: 완료/중단 항목
├── 5. Zettelkasten/
│   ├── 00. Inbox/        # 빠른 메모 (주 1회 정리)
│   ├── 10. Literature/   # 원천 노트 (저자의 생각)
│   └── 20. Permanent/    # 영구 노트 (내 통찰, 최소 2개 연결)
├── 6. Templates/          # 노트 생성 템플릿 (semver 버전 관리)
└── 7. Attachments/        # 이미지, PDF 등 바이너리 파일
```

## Frontmatter 핵심 규칙

### PARA vs ZK 차이 (중요)

| 필드 | PARA (Projects/Areas/Resources) | ZK (Literature/Permanent) |
|------|--------------------------------|--------------------------|
| `created` / `updated` | ❌ OS 메타 사용 (`file.ctime`, `file.mtime`) | ✅ 지식 진화 추적용 |
| `due` | ✅ Projects만 필수 | ❌ |
| `related` | ❌ 본문 `[[링크]]`로 처리 | ✅ Permanent는 최소 2개 필수 |
| `source` / `author` | ❌ | ✅ Literature만 |

### PARA 최소 스키마 (Projects 예시)

```yaml
type: project
status: todo            # todo | in-progress | completed | on-hold
due: 2025-12-31         # 프로젝트는 기한 필수
# area: Operations      # 허브/쿼리에 쓸 때만
# tags: [priority/high] # 0–3개
```

### ZK Literature 스키마

```yaml
type: literature
status: active
created: 2025-10-14
updated: 2025-10-14
source: ""
author: ""
```

### ZK Permanent 스키마

```yaml
type: permanent
status: active
created: 2025-10-14
updated: 2025-10-14
tags: []
related: []             # 최소 2개 이상 필수
```

### `updated` 갱신 규칙

- **ZK**: 내용 변화(아이디어 발전, 연결 추가)일 때만 — 오타/포맷팅 변경은 갱신 금지
- **Docs**: 본문 수정(절차 변경, 예시 추가)일 때만
- **PARA**: `updated` 필드 사용 안 함

## 템플릿 시스템

8개 템플릿(`project`, `project-hub`, `area`, `resource`, `literature`, `permanent`, `docs`, `archive`)이 `6. Templates/`에 있으며 semver로 버전 관리됩니다.

**템플릿 수정 시**: 버전 증가 → `6. Templates/CHANGELOG.md` 업데이트 → `6. Templates/CLAUDE.md` 레지스트리 갱신 순서 준수. Breaking Change는 기존 템플릿 수정이 아닌 신규 템플릿 생성으로 처리.

## Hub 파일

Hub 파일(`00_XXX_Hub.md`) 운영 규칙: [[0. Docs/Hub-운영-가이드]]

## 하위 폴더 운영 지침

각 폴더 작업 전 해당 CLAUDE.md를 반드시 참조하세요.

| 폴더 | CLAUDE.md 경로 | 핵심 내용 |
|------|---------------|-----------|
| 0. Docs | `0. Docs/CLAUDE.md` | `doc_type`, Frontmatter 규칙, `updated` 갱신 기준, Changelog 규칙 |
| 1. Projects | `1. Projects/CLAUDE.md` | 프로젝트 Frontmatter, 상태 정의, 태그 허용 집합 |
| 5. Zettelkasten | `5. Zettelkasten/CLAUDE.md` | Inbox/Literature/Permanent 흐름, 고아 노트 방지, ZK→PARA 복제본 원칙 |
| 6. Templates | `6. Templates/CLAUDE.md` | 템플릿 레지스트리, semver 버전 관리, Breaking Change 처리 |

## Obsidian 링크 문법

```markdown
[[노트 이름]]                  # 내부 링크
[[노트 이름|표시 텍스트]]      # 별칭이 있는 링크
[[노트 이름#제목]]             # 특정 제목으로 링크
![[이미지.png]]                # 이미지 임베드
```

## Changelog

- 2025-10-13: 초기 버전 - 간결하게 재작성 (불필요한 섹션 제거)
- 2026-04-17: 폴더명 오류 수정(Hulkeinstein→보관), 중복 Docs 섹션 제거, 하위 CLAUDE.md 목록 추가
- 2026-04-17: 대폭 간결화 - 중복 섹션 제거, PARA vs ZK Frontmatter 비교표 추가, 하위 CLAUDE.md에 위임
