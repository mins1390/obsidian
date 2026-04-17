---
# === 템플릿 메타데이터 ===
type: template
target: permanent
status: approved
version: 1.2.0
compat:
  templater: ">=1.24.0"
  obsidian: ">=1.0.0"
changelog_url: "[[6. Templates/CHANGELOG]]"
superseded_by: ""
# ===============================================

# === 실제 노트 Frontmatter ===
type: permanent
status: active
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
source: "[[]]"
# author: ""
related: ["[[]]", "[[]]"]
# tags: []
---

# <% tp.file.title %>

## 핵심 주장
<!-- 이 노트가 말하는 단 하나의 아이디어를 1-2문장으로 -->
<% tp.file.cursor(1) %>

## 내용

<% tp.file.cursor(2) %>

## 왜 중요한가
<!-- 이 아이디어가 왜 의미 있는가? 어디에 적용되는가? -->

## 연결된 생각
<!-- 최소 2개 기존 노트와 연결 (필수) -->
- [[<% tp.file.cursor(3) %>]] —
- [[<% tp.file.cursor(4) %>]] —

## 출처
- [[<% tp.file.cursor(5) %>]]
