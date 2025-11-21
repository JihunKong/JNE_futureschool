📌 API 상세 명세서

1. 사용자 인증

POST /api/auth/signup
POST /api/auth/login
GET  /api/auth/profile

2. 학습 로그

POST /api/logs
GET  /api/logs/user/:id

3. 말하기 평가

POST /api/speaking/upload
POST /api/speaking/score

4. 쓰기 첨삭

POST /api/writing/evaluate

5. 기술 용어

GET  /api/tech-words
POST /api/tech-words/upload

6. 교사용 대시보드

GET /api/teacher/students
GET /api/teacher/analytics/:studentId


⸻

🎨 Figma UI 화면 (총 10개 제안)
	1.	홈 화면
	2.	말하기 연습 화면
	3.	TOPIK 문법 학습 화면
	4.	기술 한국어 단어 학습 화면
	5.	기술 절차 말하기 화면
	6.	쓰기 첨삭 입력 화면
	7.	생활한국어 챗봇 화면
	8.	마이페이지 (내 학습 기록)
	9.	교사용 학생 리스트
	10.	학생 상세 리포트 대시보드

⸻

📁 프로젝트 파일 구조 (예시)

📦src
├── api
│   ├── auth.ts
│   ├── logs.ts
│   ├── speaking.ts
│   ├── writing.ts
├── components
│   ├── Header.tsx
│   ├── Footer.tsx
│   ├── DashboardCard.tsx
├── pages
│   ├── index.tsx
│   ├── speaking.tsx
│   ├── tech-words.tsx
│   ├── teacher.tsx
├── services
│   ├── apiClient.ts
│   ├── aiService.ts
├── lib
│   ├── whisperClient.ts
│   ├── scoringUtils.ts
├── styles
│   └── globals.css
├── types
│   └── index.ts
└── utils
    └── formatter.ts


⸻

🧠 AI 모델 Fine-Tuning 가이드

Whisper STT (음성 인식)
	•	다국적 발화자 데이터 수집
	•	Ko-Whisper 모델 기반 fine-tune
	•	사용 도구: 🤗 Transformers + openai/whisper-large + NeMo

GEC 모델 (문법 교정)
	•	학습 데이터: 외국인 한국어 학습자 코퍼스 (AIHub, TOPIK 응시자 텍스트)
	•	모델: KoBART / GPT-5-mini

쓰기 첨삭 평가 모델
	•	루브릭 기반 분류 학습
	•	입력: 에세이 + 채점 기준
	•	출력: 점수 + 피드백 문장

말하기 발음 채점 모델
	•	whisper + 음소 alignment 분석
	•	각 음소별 정확도 스코어 산출 후 Heatmap 생성

⸻

🎤 학생 음성 데이터 수집 프로토콜
	1.	동의서 받기 (디지털 동의 또는 부모 동의 포함)
	2.	수집 항목:
	•	이름(ID 익명화)
	•	모국어 / 성별 / 나이
	•	발화 음성(mp3/wav)
	•	원문 문장 텍스트
	3.	저장 위치: docker, 암호화 적용
	4.	처리:
	•	Whisper → 자막 변환
	•	발음 채점용 음소 정렬
	•	발음 오류 라벨링

⸻

📜 개인정보 보호 정책 (PIPA 기준)

수집 목적
	•	학습 분석, 개별화 피드백 제공, AI 성능 개선

수집 항목
	•	이름, 성별, 국적, 학습기록, 음성/텍스트 입력, 활동 로그

보유 기간
	•	서비스 탈퇴 후 1년 이내 파기

제3자 제공 없음
	•	어떠한 외부 기관에도 제공하지 않음

안전 조치
	•	SSL 암호화
	•	주기적 보안 점검 및 접근 통제

