# 🧭 ResearchPath

> **이공계 학부생을 위한 대학원 연구실 의사결정 도우미**  
> 흩어진 정보를 한 장의 결정카드로 — 컨택 메일 + **논문 번역기**까지 통합

[![GitHub Pages](https://img.shields.io/badge/배포-GitHub%20Pages-brightgreen?style=flat-square)](#-바로-사용하기)
[![License: MIT](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE)
[![HTML Only](https://img.shields.io/badge/기술-단일%20HTML-blueviolet?style=flat-square)](#-기술-스택)
[![Contact](https://img.shields.io/badge/문의-nina829%40naver.com-blue?style=flat-square)](mailto:nina829@naver.com)

---

## 📌 프로젝트 개요

이공계 학부생이 대학원 연구실을 알아볼 때 겪는 4가지 고통을 한 번에 해결합니다:

| 문제 | 기존 방식 | ResearchPath |
|------|-----------|--------------|
| 정보가 여러 곳에 흩어져 있음 | 홈페이지 → Scholar → 에브리타임 → 카톡 선배 | ✅ 한 화면에서 비교 |
| 논문이 영어·전문용어 | 직접 번역, 30분+ 소요 | ✅ 쉬운 한 줄 요약 + AI 번역기 내장 |
| 연구가 어떤 진로로 이어지는지 모름 | 알 수 없음 | ✅ 계약대학원·직무 연결 축 제공 |
| 첫 컨택 메일이 막막 | 시작을 못 함 | ✅ 30초 만에 맞춤 초안 + 메일앱 원클릭 |

---

## ✨ 주요 기능

### 🔍 ResearchPath (연구실 탐색 탭)

| 기능 | 설명 |
|------|------|
| 스마트 매칭 추천 | 키워드 칩 선택 + **직접 키워드 추가** + 진로 가중치 정렬 |
| 5축 결정카드 | 연구분야·논문·진로·계약대학원·AI상담을 한 카드에 |
| 논문 구글 스칼라 링크 | 대표 논문 → 구글 스칼라 직링크 클릭 |
| 컨택 메일 자동 생성 | 교수·논문·진로 맞춤 초안 |
| **네이버 메일 / Gmail 원클릭** | 제목+본문 자동 채움, 탭 오픈 |
| 태그 필터바 | 결과 화면에서 분야별 즉시 필터 |
| AI 상담 패널 | 데모 모드 + Anthropic API 연동 |
| 관리자 패널 | 비밀번호 보호, 연구실 추가·수정·삭제, localStorage 저장 |

### 📄 논문 번역기 Pro (번역기 탭)

`app2.py` 핵심 기능을 브라우저에서 바로 실행 가능하도록 통합

| 기능 | 설명 |
|------|------|
| PDF 업로드 | 드래그&드롭 · 다중 파일 · PDF.js 브라우저 내 처리 |
| AI 번역 | OpenAI GPT-4o/mini 선택 · 청크 단위 · Rate limit 재시도 |
| 수식 보존 | `__FXXXX__` 플레이스홀더 방식 (app2.py 동일 로직) |
| 번역 스타일 | 학술 격식체 / 구어체 / 기사체 / 교과서체 |
| 전문용어 병기 | 첫 등장 시 `번역어(원문)` 형태 |
| 논문 요약 | 연구목적·방법론·결과·결론·한계 구조화 |
| 핵심 키워드 | 10~15개 JSON 추출 |
| 참고문헌 정리 | 논문 말미에서 자동 파싱 |
| 번역 전/후 지시 | 추가 요청사항 입력 가능 |
| 논문 Q&A | OpenAI 또는 Claude API로 번역문 기반 질문 답변 |
| 다운로드 | TXT · HTML 형식 저장 |

> **전체 기능** (PDF/Word 저장 · 이메일 전송 · 용어집 · 히스토리 · Scholar 검색 · 2단 비교 PDF) →  
> [Paper Translator v1 (Python/Streamlit 버전)](https://github.com/lhwlhw0829-cmd/Paper-Translator-Version-1)

---

## 🚀 바로 사용하기

### GitHub Pages 배포 (권장)
```
1. 이 저장소를 Fork
2. Settings → Pages → Branch: main, /(root)
3. Save → https://[username].github.io/[repo-name]
```

### 로컬 실행 (서버 없이)
```bash
# 다운로드 후 더블클릭만 해도 됩니다
open researchpath_final.html   # macOS
start researchpath_final.html  # Windows
```

---

## 📂 파일 구성

```
ResearchPath/
├── researchpath_final.html      # ⭐ 메인 앱 (이것 하나로 완성)
│                                #    ResearchPath + 논문 번역기 통합
├── ResearchPath_Slides.pptx     # 경진대회 발표 슬라이드 (11장)
└── README.md                    # 이 파일

# Paper Translator 전체 버전 (별도 저장소)
Paper-Translator-Version-1/
├── app2.py          # Streamlit 메인 앱
├── requirements2.txt
└── README.md
```

---

## 🛠️ 기술 스택

### ResearchPath 웹앱 (`researchpath_final.html`)

| 항목 | 내용 |
|------|------|
| 구조 | 단일 HTML (HTML/CSS/JS 인라인, 빌드 불필요) |
| PDF 처리 | PDF.js CDN (브라우저 내 텍스트 추출) |
| AI 연동 | Anthropic Messages API · OpenAI Chat Completions |
| 저장 | localStorage (연구실 데이터, API 키) |
| 배포 | GitHub Pages / 정적 파일 서버 / 로컬 더블클릭 |
| 외부 의존 | Pretendard 폰트 (Google Fonts CDN), PDF.js |

### Paper Translator v1 (`app2.py`)

| 항목 | 내용 |
|------|------|
| 프레임워크 | Python · Streamlit |
| AI | OpenAI GPT-4o/mini · Anthropic Claude |
| PDF | PyMuPDF (fitz) |
| 출력 | ReportLab (PDF) · python-docx (Word) |
| Scholar | scholarly 라이브러리 |

---

## ⚙️ 관리자 패널 (연구실 데이터 관리)

앱 우측 상단 **⚙ 관리자** → 비밀번호 `admin1234` → 연구실 추가/수정/삭제

입력 항목:
```
연구실 이름, 교수명, 소속 학과
관련 태그 (쉼표 구분) ← 검색 칩에 자동 반영
연구 방향, 대표 논문 제목
논문 구글 스칼라 검색 키워드
논문 쉬운 한 줄 요약
연결 직무 / 계약대학원 정보
연구실 홈페이지 URL (선택)
```

---

## 🤖 AI 기능 활성화

### ResearchPath AI 상담
1. [Anthropic Console](https://console.anthropic.com/)에서 API 키 발급
2. AI 상담 탭 → API 키 입력 → 저장
3. 이후 자동 유지 (localStorage)

### 논문 번역기 AI
1. [OpenAI Platform](https://platform.openai.com/)에서 API 키 발급
2. 번역기 탭 상단에 입력
3. Q&A는 Claude API 키도 사용 가능

> API 없이도 **데모 모드**로 주요 기능 체험 가능

---

## 🗺️ 로드맵

- [ ] 논문 PDF/Word 다운로드 (Python 백엔드 없이)
- [ ] 연구실 즐겨찾기 / 비교 저장
- [ ] 모바일 PWA 전환
- [ ] 실제 연구실 데이터 크라우드소싱
- [ ] arXiv API 연동 (최신 논문 자동 추가)
- [ ] 이메일 전송 기능 (EmailJS 활용)

---

## 🤝 기여 / 데이터 제공

연구실 정보를 추가하고 싶으신가요?
- Issue를 열어 연구실 정보를 남겨주세요
- 또는 직접 연락: nina829@naver.com

---

## 📜 라이선스

MIT License — 자유롭게 사용·수정·배포 가능

---

## 💌 만든 이

**이혜원 (Hyewon Lee)**  
AI·빅데이터학과  
📧 [nina829@naver.com](mailto:nina829@naver.com)  
🔗 자매 프로젝트: [Paper Translator v1](https://github.com/lhwlhw0829-cmd/Paper-Translator-Version-1)

> *"인맥 있는 학생만 좋은 연구실을 아는 구조를 바꾸고 싶었어요."*
