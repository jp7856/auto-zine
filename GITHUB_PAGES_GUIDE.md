# 🚀 오토진 - GitHub Pages 설정 가이드

## 프로젝트 구조

```
auto-zine/
├── docs/                    # GitHub Pages 공개 폴더
│   ├── index.html          # 메인 페이지
│   ├── style.css           # 스타일시트
│   ├── article-junior.html
│   ├── article-kids.html
│   ├── article-kinder.html
│   └── article-times.html
├── articles/               # 원본 마크다운 기사
├── html/                   # 로컬 미리보기용 (git 제외)
└── ...
```

## GitHub Pages 활성화 방법

### 1. GitHub에 저장소 푸시
```bash
git add .
git commit -m "Add GitHub Pages docs folder"
git push origin main
```

### 2. GitHub 저장소 설정
1. 저장소의 **Settings** 탭 열기
2. 좌측 메뉴에서 **Pages** 클릭
3. **Source** 섹션에서:
   - Branch: `main`
   - Folder: `docs` 선택
4. **Save** 클릭

### 3. 사이트 확인
몇 분 후 GitHub Pages 설정 아래에 다음과 같은 형식의 URL이 표시됩니다:
```
https://your-username.github.io/auto-zine/
```

## 로컬 미리보기

### Windows에서 간단한 서버 실행
```bash
# Python 3 사용 시
python -m http.server 8000 --directory docs

# 브라우저에서 열기
http://localhost:8000
```

또는 VS Code 확장 프로그램 사용:
- **Live Server** 확장 설치
- `docs` 폴더의 `index.html` 우클릭
- "Open with Live Server" 선택

## 파일 추가/수정 방법

### 새 기사 추가 시
1. `articles/` 폴더에 마크다운 파일 작성
   ```
   articles/category/YYYY-MM-DD-title.md
   ```

2. `docs/` 폴더에 HTML 파일 생성
   ```html
   <!DOCTYPE html>
   <html lang="ko">
   <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>제목 - 오토진</title>
     <link rel="stylesheet" href="style.css">
   </head>
   <body>
     <!-- index.html과 동일한 헤더/네비 구조 -->
     <!-- 내용 추가 -->
   </body>
   </html>
   ```

3. `docs/index.html`의 카드 섹션에 링크 추가

## 주요 특징

✅ **반응형 디자인** - 모바일, 태블릿, 데스크톱 모두 지원  
✅ **빠른 로딩** - 정적 HTML 사용  
✅ **SEO 친화적** - 적절한 메타 태그 포함  
✅ **오프라인 접근 가능** - GitHub Pages는 무료 호스팅

## 수정 후 배포

변경사항이 있으면:
```bash
git add docs/
git commit -m "Update article content"
git push origin main
```

GitHub Pages는 자동으로 변경사항을 반영합니다 (1-2분 소요).

---

**Note**: `html/` 폴더는 로컬 개발용이며, `.gitignore`에 의해 git에서 제외됩니다.
