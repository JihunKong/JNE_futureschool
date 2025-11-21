전남미래국제학교 학생들의 특성과에 맞는 “완성형 통합 AI 한국어 학습 시스템”

포함된 문서 목록
	1.	PRD(제품 요구사항 문서)
	2.	UX 플로우 + 와이어프레임
	3.	AI 모델 구조 & 전체 inference 흐름
	4.	ERD
	5.	DB 스키마 상세
	6.	시스템 아키텍처
	7.	기술 스택
	8.	전체 스펙 & API 예시
	9.	초기 개발 로드맵

📘 1. PRD (Product Requirements Document)

제품명

Tech-Korean AI Learning System (TKALS)
기술교육 + 한국어 교육 + AI 기반 맞춤학습 통합 플랫폼

⸻

🟦 1.1 제품 목표

외국 학생(몽골·카자흐·우즈벡·베트남)의 한국어 습득 속도를 2~3배 향상시키고,
기술 교육 참여에 필요한 ‘기술 한국어’를 자동으로 제공하는 AI 기반 학습 플랫폼 구축.

핵심 목표
	•	TOPIK 2 → 4 수준 도약
	•	발음/말하기 정확도 실시간 개선
	•	기술(PBL) 수업 연동 한국어 제공
	•	학생별 학습 데이터 자동 수집 → 맞춤 학습 강화
	•	교사 업무 자동화(리포트, 학생 분석, 추천 수업 생성)

⸻

🟩 1.2 주요 사용자

사용자	목표	필요 기능
외국인 학생	한국어 능력 향상, 기술 수업 참여	발음/말하기 AI 피드백, TOPIK 학습, 기술 한국어
국어/한국어 교사	학생 분석/피드백 자동화	학생 분석 대시보드, 오류 패턴, 추천 수업
기술 교사	한국어가 약한 학생 지원	기술 용어 해석, 절차 설명
관리자	운영 모니터링	학습기록 DB 조회, 보고서


⸻

🟧 1.3 주요 기능 요약

① 학습자 분석 엔진
	•	초기 수준 진단(TOPIK 간이 테스트)
	•	모국어 기반 예상 오류 패턴 분석
	•	음성 분석(발음 정확도)
	•	기술 수업 언어 요구 자동 분석(교과자료 업로드 기반)

② AI 발음/말하기 교정기
	•	Whisper 기반 음성 인식
	•	TTS 기반 대화형 말하기 연습
	•	발음/문법/담화 기능 자동 교정
	•	TOPIK 말하기 모의시험 자동 생성 및 채점

③ TOPIK 전용 학습 모듈
	•	문법/어휘 학습
	•	듣기 생성형 문제
	•	읽기 지문 난이도 변환
	•	쓰기 자동 첨삭(문법/조직력 점수화)

④ 기술 한국어 모듈
	•	실습보고서 자동 생성 가이드
	•	기술 용어 사전
	•	절차 설명 말하기 훈련

⑤ 생활한국어 모듈
	•	역할극 챗봇
	•	기숙사 문제 해결 대화
	•	학교 규정 이해 기능

⑥ 교사용 대시보드
	•	학생별 AI 분석
	•	발음 점수 변화
	•	쓰기 루브릭 기반 평가
	•	다음주 수업 추천
	•	자동 보고서(PDF)

⸻

🟨 1.4 KPI
	•	TOPIK 합격률
	•	말하기 완료 횟수
	•	발음 정확도(%) 향상
	•	기술한국어 어휘수 증가량
	•	학생별 학습 시간
	•	과제 제출률
	•	교사용 보고서 자동 생성 시간 절감

⸻

📐 2. UX 플로우 & 와이어프레임

⸻

🟦 2.1 앱 전체 사용자 흐름(Flowchart)

[로그인]
    ↓
[레벨 테스트]
    ↓
[학습자 프로파일 생성]
    ↓
[오늘의 학습 홈]
    ├─ TOPIK 학습
    ├─ 기술 한국어 학습
    ├─ 말하기/발음 훈련
    ├─ 생활 한국어
    ├─ 단어 복습
    ↓
[AI 대화형 학습]
    ↓
[학습 기록 저장]
    ↓
[교사 대시보드]


⸻

🟩 2.2 핵심 화면 와이어프레임 (텍스트 기반)

🏠 HOME

+-----------------------------------------+
|  오늘의 추천 학습                       |
|  - 말하기 연습 5분                      |
|  - 기술 단어 10개                       |
|  - TOPIK 듣기 3문제                     |
|                                         |
|  내 학습 현황                           |
|  LEVEL: TOPIK 2.6                       |
|  발음 정확도: 68%                       |
+-----------------------------------------+
| 하단 메뉴                                |
| [학습] [말하기] [기술] [사전] [내정보]   |
+-----------------------------------------+

🗣️ 말하기 AI 화면

[문장 제시] "전원을 연결하세요."
[학생 발화 버튼] 🎤 누르고 말하기
[AI 피드백]
 - 발음 점수: 72%
 - 문제된 소리: ㄹ → rl 발음 약함
 - 추천 문장: "전원을 먼저 연결해 주세요."

📘 TOPIK 학습

문법: -(으)니까
예문 5개  
→ 변형하기  
→ 말하기 연습  
→ 짧은 문제 3개

🛠️ 기술 한국어

[오늘의 기술 단어]
센서 / 회로 / 업로드하다 / 배선 / 오작동

[절차 설명 말하기]
"아두이노 코드를 업로드하는 방법을 말해보세요."
AI: 실시간 문법·단어 피드백

📊 교사용 대시보드

학생 목록
- 김OO: 발음 68% → 74%, 문법 오류 12→7
- Aitgul: 말하기 횟수 4회, 기술단어 30개 암기

학생 상세
- 오류 패턴 그래프
- 학습시간 그래프
- 추천 지도안 다운로드(PDF)


⸻

🤖 3. AI 모델 구성 및 학습 흐름

⸻

🟦 3.1 전체 AI 구성도

[음성입력] → Whisper (STT)
                ↓
        AI Korector (발음/문법 분석)
                ↓
          Feedback Generator
                ↓
           사용자 UI

[텍스트 입력] → GPT 계열 모델
                ↓
      문법/어휘/쓰기 첨삭
                ↓
            학습 콘텐츠 생성


⸻

🟩 3.2 AI 모델 구성요소

① 음성 인식 모델 (STT)
	•	Whisper-large 또는 WhisperX
	•	한국어 + 다국적 억양 음성 fine-tuning

② 발음 평가 모델
	•	한국어 음소 단위 alignment 모델
	•	오류 라벨링:
	•	ㄹ/ㄴ 혼동
	•	받침 미실현
	•	장단음
	•	초성 파열음 등

③ 문법 오류 탐지 모델(GEC: Grammatical Error Correction)
	•	GPT-5-mini + Instruction tuning
	•	문법 유형 40개 분류

④ 읽기 난이도 변환 모델
	•	Rewriting Model
	•	쉬운 한국어 ↔ 표준 한국어 두 버전 생성

⑤ 쓰기 자동 채점 모델
	•	TOPIK 쓰기 루브릭 기반
	•	채점 항목:
	•	내용
	•	조직
	•	문법
	•	단어 다양성
	•	문장 정확성

⑥ 기술 한국어 추출 모델
	•	기술 수업 자료에서
	•	명사/용어
	•	절차 문장
	•	주제 키워드
자동 추출하는 NER+Summarizer 모델

⑦ 추천 시스템
	•	학생 패턴 기반 학습 추천(MLP or LightGBM)
	•	개인화 로드맵 생성

⸻

🟧 3.3 AI 전체 학습 흐름
	1.	데이터 수집

	•	학생 음성
	•	발음 오류
	•	문법 오류
	•	기술 수업 자료
	•	학습 로그

	2.	데이터 정제

	•	음성 정렬
	•	문장/문법 라벨 생성
	•	기술 용어 필터링

	3.	모델 학습

	•	STT → 적응
	•	발음 평가 → 대조 학습
	•	문법 오류 → 수퍼바이즈드 학습
	•	추천 알고리즘 → 사용자 로그 기반 학습

	4.	모델 결합

	•	음성→문법→피드백→추천 순환 구조

⸻

🗄️ 4. ERD + DB 구조

⸻

🟦 4.1 ERD 개요

┌───────────┐        ┌─────────────┐
│   Users    │ 1    n │   LearningLogs│
└───────────┘        └─────────────┘
      │                       │
      │1                    n │
┌───────────┐        ┌──────────────────┐
│TechWords  │        │PronunciationLogs │
└───────────┘        └──────────────────┘
      │
      │
┌────────────┐
│TopikResults│
└────────────┘


⸻

🟩 4.2 테이블 상세

Users

column	type	note
id	PK	학생 ID
name	string	
nationality	string	몽/카/우/베
level	float	TOPIK 1~4
createdAt	datetime	


⸻

LearningLogs

column	type
id	PK
userId	FK
module	enum(‘TOPIK’, ‘TECH’, ‘SPEAK’, ‘LIFE’)
timeSpent	int
score	float
contentId	FK
createdAt	datetime


⸻

PronunciationLogs

column	type
id	PK
userId	FK
sentence	text
score	float
errorType	json
audioPath	string


⸻

TechWords

| word | string |
| meaning | text |
| difficulty | int |
| exampleSentence | text |

⸻

TopikResults

| userId | FK |
| reading | float |
| listening | float |
| writing | float |
| speaking | float |
| createdAt | datetime |

⸻

🖥️ 5. 시스템 아키텍처

⸻

🟦 백엔드 구조

[Client App]
    ↓  HTTPS
[API Gateway]
    ↓
[Auth Service]
[Learning Service] (Next.js or FastAPI)
[AI Service Layer]
    ├─ STT Server(Whisper)
    ├─ LLM Server(GPT, vLLM)
    ├─ Scoring Engine
    └─ Rewriting Engine
[PostgreSQL or MySQL]
[Object Storage(S3)]


⸻

🟩 프런트엔드 구조
	•	Next.js
	•	React Native (모바일)
	•	Zustand/Recoil for state
	•	Tailwind
	•	Figma 기반 UI 시스템

⸻

🛠️ 6. 기술 스택

Front
	•	Next.js 14
	•	React Native
	•	TypeScript
	•	Tailwind
	•	Expo

Back
	•	FastAPI + Python
	•	Node.js (Next.js API routes)
	•	Redis 캐싱
	•	PostgreSQL
	•	Prisma ORM

AI
	•	OpenAI GPT-5
	•	WhisperX
	•	vLLM + QLoRA로 파인튜닝
	•	HuggingFace Transformers
	•	SentencePiece
	•	KoBERT for 문장 난이도 분석

Infra
	•	AWS
	•	EC2
	•	S3
	•	RDS(PostgreSQL)
	•	Lambda (음성 전처리)
	•	API Gateway
	•	CloudFront
	•	Container
	•	Docker
	•	Docker Compose
	•	Kubernetes(EKS) 가능

⸻

⚙️ 7. 전체 시스템 스펙

① AI 말하기
	•	STT 정확도 95%
	•	발음 평가 0~100점
	•	발음 오류 음소 단위 표시

② TOPIK 문법
	•	40문형 필수 제공
	•	자동 문제 생성
	•	오답 노트 자동 관리

③ 기술한국어
	•	교과자료 pdf 업로드 → 자동 용어 추출
	•	기술 절차 → 자동으로 말하기 템플릿 변환

④ 학습 데이터 기록
	•	활동 로그 전부 DB 저장
	•	음성 파일 S3 저장
	•	문법 오류 json 저장
	•	발음 점수 히트맵 생성

⑤ 교사용 도구
	•	학생 레벨 자동 산출
	•	개별 피드백 자동 생성
	•	평가 리포트 PDF 생성

⸻

🧭 8. 개발 로드맵 (완성형 통합 버전)

Phase 1. MVP (6~8주)
	•	음성녹음 + STT
	•	문법/단어 학습
	•	TOPIK 문제
	•	기본 DB

Phase 2. AI 통합 (8~12주)
	•	발음 평가
	•	쓰기 첨삭
	•	기술한국어 모듈 1차

Phase 3. 통합 버전 (12~20주)
	•	대시보드
	•	기술 수업 연동
	•	추천 엔진
	•	보고서 자동화

Phase 4. 안정화 + 고도화 (20주~)
	•	모델 파인튜닝
	•	반자동 평가
	•	음성 기반 대화학습
