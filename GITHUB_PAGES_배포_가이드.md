# 🚀 GitHub Pages 무료 정적 웹 호스팅 원클릭 배포 가이드

본 가이드는 본 디렉터리의 통합 포트폴리오 웹사이트(`index.html`)와 8개 프로젝트 세부 포트폴리오를 **GitHub Pages**를 통해 전 세계 어디서든 접속 가능한 무료 웹사이트(`https://<아이디>.github.io/<저장소명>/`)로 배포하는 절차를 안내합니다.

---

## 📌 0. 사전 준비 사항
- **GitHub 계정** (없으신 경우 https://github.com 에서 무료 가입)
- **Git 클라이언트** (Git for Windows 또는 VS Code 내장 Git)

---

## 🛠️ 1. 단계별 배포 절차 (소요 시간: 약 3분)

### 1단계: GitHub에서 새 저장소(Repository) 생성
1. GitHub 웹사이트에 로그인 후 우측 상단의 **`+`** 버튼 → **[New repository]**를 클릭합니다.
2. 저장소 이름을 입력합니다.
   - 예: `portfolio` 또는 `ai-engineering-portfolio`
3. 공개 범위(Visibility)는 **`Public`**을 선택합니다. (무료 계정에서 GitHub Pages 배포 시 Public 필수)
4. `Add a README file`, `.gitignore` 등은 **체크 해제**한 채로 하단의 **[Create repository]** 버튼을 누릅니다.

---

### 2단계: 로컬 포트폴리오 폴더에서 Git 초기화 및 Push
현재 포트폴리오 폴더(`_포트폴리오`)에서 PowerShell 또는 터미널을 열고 아래 명령어를 순서대로 실행합니다:

```powershell
# 1. 포트폴리오 루트 디렉터리로 이동 (현재 위치 확인)
# cd C:\Users\scinn\Documents\#취성패\포트폴리오\_포트폴리오

# 2. Git 저장소 초기화
git init

# 3. 기본 브랜치를 main으로 설정
git branch -M main

# 4. 전체 파일 스테이징
git add .

# 5. 첫 커밋 생성
git commit -m "feat: Initial commit for integrated portfolio website"

# 6. 생성한 GitHub 원격 저장소 연결 (본인의 계정명과 저장소명으로 변경)
# 예: https://github.com/your-username/portfolio.git
git remote add origin https://github.com/<본인-GitHub-아이디>/<저장소이름>.git

# 7. GitHub로 푸시
git push -u origin main
```

> [!NOTE]
> 만약 특정 프로젝트의 용량이 큰 바이너리 파일(예: `.dump`, `.pt`, `.pth`, `.jar` 등)이 포함되어 GitHub 100MB 파일 용량 제한에 걸리는 경우, 포트폴리오 열람용 웹 에셋(`포트폴리오.html`, `index.html`, 이미지 폴더들)만 올리시면 됩니다. `.gitignore`에 대용량 가중치(`*.pt`, `*.pth`, `*.dump`)를 제외하고 푸시하시면 즉시 통과됩니다.

---

### 3단계: GitHub Pages 호스팅 활성화
1. GitHub 웹사이트의 해당 저장소 페이지로 이동합니다.
2. 상단 탭에서 **[Settings]** (설정)을 클릭합니다.
3. 좌측 사이드바 메뉴에서 **[Code and automation]** → **[Pages]**를 클릭합니다.
4. **Build and deployment** 섹션 설정:
   - **Source**: `Deploy from a branch` 선택
   - **Branch**: `main` 브랜치 선택 / 폴더는 `/(root)` 선택
   - 우측의 **[Save]** 버튼 클릭!
5. 1~2분 정도 기다리시면 상단에 배포 완료 알림 메시지와 함께 웹사이트 URL이 나타납니다:
   ```text
   Your site is live at https://<본인-GitHub-아이디>.github.io/<저장소이름>/
   ```

---

## 🌟 2. 배포 구조 메모

1. **루트 `index.html` = 허브 페이지**
   - 대표 프로젝트(01 의정이슈레이더, 02 Pet Log) → 실무 프로젝트(OCR Agent 관리자 웹, OCR 뷰어 웹 전환) → 기타 프로젝트 4개 → 기술 스택 순서입니다.
   - 외부 의존성은 Pretendard 웹폰트(jsDelivr) 하나뿐이고, 스타일은 페이지 안에 직접 작성되어 있습니다(라이트/다크 지원).
2. **카드 썸네일은 `assets/thumbs/*.webp`**
   - 원본 스크린샷(최대 1.5MB) 대신 15~65KB WebP를 씁니다. 원본 이미지를 바꾸면 썸네일도 다시 만들어야 합니다.
3. **`.nojekyll`**
   - Jekyll 처리를 끄므로 한글 폴더명과 `_`로 시작하는 경로가 그대로 서빙됩니다.
4. **상대 경로**
   - 모든 링크가 상대 경로라 저장소 이름(`/<저장소이름>/`)이 무엇이든 동작합니다.
5. **`.gitignore`로 제외되는 것**
   - `_backup/`(이전 index.html), `포트폴리오_수정전_백업.html`(약 6MB), QuestForge `_이전_목업/`, `.claude/`
6. **배포 전 로컬 확인**
   - 폴더에서 `python -m http.server 5500 --bind 127.0.0.1` 실행 후 http://127.0.0.1:5500 접속

---

## 💡 3. 이력서 및 링크 공유 팁
- 이력서(Notion, 사람인, 잡코리아, 원티드)나 링크드인 프로필에 아래와 같이 기재하시면 가장 좋습니다:
  - **포트폴리오 링크:** `https://<본인-GitHub-아이디>.github.io/<저장소이름>/`
  - **소개:** "AI Agent, 대규모 RAG 및 엔터프라이즈 풀스택 프로젝트 8종 통합 포트폴리오 웹사이트"
