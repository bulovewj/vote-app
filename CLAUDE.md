# 학급 투표 앱

## 개요
- 6학년 교실에서 실제로 쓰는 익명 투표 앱
- 교사가 질문을 등록하면 학생이 폰으로 투표하고, 결과를 실시간 집계로 본다
- 단일 index.html + Supabase 저장

## 기술 스택
- HTML/CSS/JS 단일 파일 (index.html) — 프레임워크 없음
- Supabase (테이블: vote_records) — 투표 데이터 저장/실시간 구독
- config.js — Supabase URL/anon key 분리 (git에 올리지 않음)

## 폴더 구조
```
/
├── index.html      # 전체 앱 (화면, 로직 모두 포함)
├── config.js       # Supabase 접속 정보 (gitignore 대상)
├── config.example.js  # config.js 형식 예시 (git에 포함, 실제 키는 없음)
└── .gitignore      # config.js 제외
```

## 코딩 컨벤션
- index.html 하나로 유지. 200줄 넘어가면 <script> 안에서 섹션 주석으로 구획만 나누고, 별도 JS 파일 분리는 먼저 물어볼 것
- 함수/변수명은 한글 주석 + 영어 camelCase
- 화면 전환은 DOM show/hide 방식 (라우팅 라이브러리 쓰지 않음)
- localStorage 키는 `voteApp_` 접두사로 통일

## 하지 말 것
- 새 라이브러리/CDN 스크립트 추가 전 반드시 물어볼 것
- 학생 개인정보(이름, 번호 등) 어떤 형태로도 수집·저장 금지 — 완전 익명 유지
- Supabase 프로젝트를 마일스톤 4(GitHub 배포) 이전에 만들지 말 것 — 순서 절대 준수
- 지시받지 않은 파일 수정 금지
- any성 임시 땜질 코드 남기지 말고, 안 되면 안 된다고 보고할 것

## 현재 상태 (마일스톤 진행표)
| 단계 | 내용 | 상태 |
|---|---|---|
| 1 | 화면 뼈대 | ✅ 완료 |
| 2 | 로컬 저장 기능 완성 | ✅ 완료 |
| 3 | Supabase 연동 코드 작성 | ✅ 완료 (코드 리뷰 대기) |
| 4 | GitHub 배포 | ⬜ 미착수 |
| 5 | Supabase 프로젝트 생성·연결 | ⬜ 미착수 |

## 참조
상세 화면/기능 명세는 `docs/작업지시서.md`, 단계별 실행 계획과 확인 방법은 `마일스톤.md`. 필요할 때만 열어볼 것.
