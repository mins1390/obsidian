# 7. Attachments 폴더

## 목적과 역할

**이미지, PDF 등 바이너리 첨부 파일**을 보관하는 폴더입니다.
마크다운 노트와 첨부 파일을 분리하여 볼트를 깔끔하게 유지합니다.

## 어떤 파일이 들어가는가

- 이미지 파일 (`.png`, `.jpg`, `.gif`, `.svg`)
- PDF 문서 (`.pdf`)
- 오디오/비디오 파일
- 기타 바이너리 파일

## 작업 방식과 규칙

1. **자동 저장 설정**: Obsidian 설정 > Files & Links > Default location for new attachments를 `7. Attachments`로 지정
2. **정기 정리**: 사용하지 않는 첨부 파일 주기적 삭제
3. **Git LFS 고려**: 대용량 파일은 Git LFS 사용 권장
4. **파일명 규칙**: 의미 있는 이름 사용 (예: `20251013-프로젝트-다이어그램.png`)

### Obsidian 설정

```
설정 → Files & Links
  → Default location for new attachments: In the folder specified below
  → Attachment folder path: 7. Attachments
```

### .gitignore 권장 설정

대용량 파일이 많은 경우:
```
7. Attachments/*.pdf
7. Attachments/*.mp4
7. Attachments/*.mov
```
