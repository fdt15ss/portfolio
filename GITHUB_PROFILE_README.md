## Hi there 👋
**AI Agent · RAG · 풀스택 웹** 개발자 임경빈입니다.

OCR 솔루션 회사에서 관리자 웹과 문서 뷰어를 풀스택으로 개발해 금융권 고객사에 납품했고,
지금은 **"숫자는 코드와 통계 모델이 계산하고, LLM은 근거를 설명한다"** 는 원칙으로 결과를 검증할 수 있는 AI 시스템을 만들고 있습니다.

🔗 **통합 포트폴리오 → https://fdt15ss.github.io/portfolio/**

#### 🧘 Core Competency
- 약간의 완벽주의자 경향으로 UI/UX를 고려하여 눈에 잘 띄지 않는 버그에 대해서도 고민하면서 개발함
- 몰입 능력이 뛰어나서 시간 가는 줄 모르고 개발함. 한번에 프로젝트를 완성은 못해도 모듈 기능 하나 함수라도 완성을 해야 직성이 풀리는 성향
- 감으로 고르지 않고 직접 비교해서 결정함 — 벡터 DB·한국어 로컬 LLM 6종을 같은 조건에서 측정해 선택
- 실무 경력 **2021.04 – 2022.06** : OCR 솔루션 웹을 개발하여 하나은행, 기업은행에 납품
- 스택오버플로우를 사용할 정도의 IT영어 능력은 있음 (20261123 현재, 스오플 포인트 537) : https://stackoverflow.com/users/16527606/niddddddfier

#### 🛠 보유 스킬
- **AI · LLM · 검색**
  - LangGraph, LangChain => Agent 파이프라인, 모델 예비 경로(fallback)
  - RAG => PostgreSQL + pgvector, BM25, RRF, BGE Reranker, ChromaDB, FAISS
  - LLM => Ollama(A.X-4.0, Gemma), OpenAI, Gemini
- **Deep Learning / Machine Learning**
  - PyTorch => ConvNeXt, KLUE RoBERTa, Grad-CAM++, Optuna
  - Tensorflow
  - Scikit-learn => tree, XGBoost / 통계 모델 => Poisson Regression
  - CV => OpenCV, MediaPipe Face Mesh, LAB 색공간 분석, face detection/comparison/gender check (VGG-Face)
- **Backend**
  - Python => FastAPI(REST, WebSocket, Pydantic), Flask, Pandas
  - Node.js => Express, node-schedule (실무)
  - Java => Spring Boot, WebClient (실무)
- **Frontend**
  - Vue.js 2, Nuxt.js (실무) / React 19, Next.js 16, TypeScript
  - Canvas, PDF.js, tiff.js (실무), ApexCharts, Tailwind CSS
- **DB**
  - PostgreSQL, MariaDB(실무), MySQL, Oracle SQL, SQLite
- **DevOps · 운영**
  - Docker, PM2, WAS(WAR) 배포, Linux(Ubuntu), Shell Script, cmd
- **Test · 협업**
  - pytest, Vitest, Playwright, Git

---

## ✨ 대표 프로젝트

#### 🏛️ 의정이슈레이더 (Council Issue Radar) — 국회도서관 2026 DATA·AI 분석 경진대회 출품작
2024–2025년 전국 17개 광역의회 회의록을 분석해, 정책 이슈가 어느 의회에서 처음 나왔고 다른 의회로 어떻게 이어졌는지 시간순으로 보여주고 다음 달 논의량을 예측하는 시스템입니다. 회의록은 외부 AI API로 보내지 않고 **모든 모델을 로컬에서 실행**합니다.

* **205만 발언 → 90만 청크** : 로컬 LLM으로 의회별 HTML 규칙화, 자식(검색)·부모(답변) 청크 분리 후 pgvector 적재
* **하이브리드 검색** : 의미 검색 + BM25를 RRF로 결합 → BGE 재순위 → Union-Find로 이슈 타임라인 생성
* 조건 벡터 검색 중앙값 **3.97ms** (ChromaDB 대비 약 148배) · 논의 지속 예측 **F1 0.881** · 언급량 예측 **MAE 7.12건**

`PostgreSQL + pgvector` `BM25 · RRF` `BGE Reranker` `Poisson Regression` `Ollama` `FastAPI`

🔗 [포트폴리오 자세히 보기](https://fdt15ss.github.io/portfolio/%EC%9D%98%EC%A0%95%EC%9D%B4%EC%8A%88%EB%A0%88%EC%9D%B4%EB%8D%94_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html)

#### 🐾 Pet Log (펫로그) — AI Agent 반려동물 케어 · 4인 팀
말하듯 남긴 기록을 AI가 항목별로 정리하고, 주의 안내·일정 알림·맞춤 상품 추천·동물병원 찾기까지 보호자의 다음 행동으로 이어주는 서비스입니다. **백엔드 · AI Agent · 외부 API 연동** 담당.

* 쇼핑 추천 Agent를 LangGraph 4단계로 재구성해 단계별 테스트 가능하게 개선
* Naver Shopping·Google Places 연동에 대체 결과·캐시·호출 제한을 붙여 API 실패에도 화면이 멈추지 않게 구현
* GPT-5-mini → 예비 GPT → Gemini → 로컬 Gemma(Ollama) 자동 전환 구조

`Next.js 16` `FastAPI` `LangGraph` `SQLite` `ChromaDB` `Ollama`

🔗 [포트폴리오 자세히 보기](https://fdt15ss.github.io/portfolio/Pet_Log_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html)

---

## 💼 실무 프로젝트 (2021.04 – 2022.06 · OCR 솔루션 웹 개발)

| 프로젝트 | 내용 | 기술 |
|---|---|---|
| [**OCR Agent 관리자 웹 UI 개선**](https://fdt15ss.github.io/portfolio/OCR_Agent_%EC%9B%B9_UI_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html)<br>풀스택 · 약 10개월 · 2021 금융권 납품 | 조회만 되던 관리자 화면을 서버 모니터링·통계·SSO·장애 알림·계정 보안을 갖춘 다중 서버 관리 도구로 확장. 외부 업체 4명 요구사항·스토리보드 작성 | Node.js, Express, Nuxt.js, MariaDB, PM2 |
| [**OCR 뷰어 웹 전환 · 결과 검수 화면**](https://fdt15ss.github.io/portfolio/OCR_%EB%B7%B0%EC%96%B4_%EC%9B%B9_UI_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html)<br>웹 파트 단독 · 약 4개월 · WAS 배포 | C# 데스크톱 뷰어를 Vue.js 웹으로 전환. 회전 좌표 재계산·Ray casting으로 이미지 ↔ 결과값 양방향 이동, IE11 대응, Spring Boot 중계 서버 | Vue.js 2, Canvas, PDF.js, Spring Boot |

---

## 🧩 기타 프로젝트

| 프로젝트 | 내용 | 기술 |
|---|---|---|
| [**QuestForge Agent**](https://fdt15ss.github.io/portfolio/QuestForge_Agent_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html) · 개인 | 게임 상태를 보고 퀘스트를 만드는 AI Agent. 수량·보상은 서버 규칙이, 문장은 LLM이 담당. 처리 경로 추적 화면 | LangGraph, FastAPI WebSocket, React 19, pytest 244 · Vitest 36 |
| [**Style.ai**](https://fdt15ss.github.io/portfolio/Style_AI_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html) · 3인 · 17일 | 사진으로 퍼스널 컬러(12톤)·체형 분석 후 상품 6,096건 중 코디 3세트 + 가상 피팅. A4 화이트밸런스 보정·퍼스널 컬러 분석 직접 구현, FastAPI 통합 | MediaPipe, K-Means · LAB, SigLIP · FAISS, GPT-4o |
| [**지능형 민원처리 시스템**](https://fdt15ss.github.io/portfolio/%EC%A7%80%EB%8A%A5%ED%98%95_%EB%AF%BC%EC%9B%90%EC%B2%98%EB%A6%AC_%EC%8B%9C%EC%8A%A4%ED%85%9C_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html) · 4인 | 민원 문장으로 기관·부서·필요 서류(192개 라벨) 추천. ConvNeXt-Small 기반 전입신고서 14칸 기입 판별 모델 학습과 Grad-CAM++ 분석 담당 ([발표 자료](https://docs.google.com/presentation/d/1IGFG29ZNeSHyzhLgli-7Fsw569P_K6iv/edit?usp=sharing&ouid=110670168050652598032&rtpof=true&sd=true)) | PyTorch, ConvNeXt-Small, KLUE RoBERTa, Optuna |
| [**디지털 샤머니즘 데이터 분석**](https://fdt15ss.github.io/portfolio/%EB%94%94%EC%A7%80%ED%84%B8_%EC%83%A4%EB%A8%B8%EB%8B%88%EC%A6%98_%EB%8D%B0%EC%9D%B4%ED%84%B0_%EB%B6%84%EC%84%9D_%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4/%ED%8F%AC%ED%8A%B8%ED%8F%B4%EB%A6%AC%EC%98%A4.html) · 4인 | 검색 트렌드 60개월·운세 앱 리뷰 6,925건·커뮤니티 글 분석. 데이터 수집·정제와 EDA 담당 | Selenium, KoNLPy, Apriori, NetworkX |
| [**얼굴 동일인 · 성별 판별 시스템**](https://speckled-bite-094.notion.site/S6-Project-2-fd8f54ba48794cccaccff8cadc2f8d80) | 얼굴 이미지 동일인 여부 판별 및 성별 분류. 전처리·학습·추론 파이프라인 직접 설계 | PyTorch, VGG-Face |

---

#### 📚 코드스테이츠 AI 부트캠프 학습 정리
머신러닝, 딥러닝, 데이터 분석 등 AI 기술 스택 학습 기록 → [학습 기록 보기](https://speckled-bite-094.notion.site/AI-39b5052c888d4ab381b55357e5feb997)

<!--
**Imkyeongbin/Imkyeongbin** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
-->
