# LG CNS 5기 미니 프로젝트 정리 — D3 · mermaid

LG CNS AM Inspire Camp 5기 미니 프로젝트 2개 정리: 전체 작업과 박주형 프론트엔드 담당 정리.

- **미니 프로젝트 1 — mermaid (mermAid)**: 2026-07-10 ~ 07-27, SJY051/mermaid
- **미니 프로젝트 2 — D3 (D³)**: 2026-08-13 ~ 08-19, SJY051/D3
- 박주형 GitHub: [david3123123](https://github.com/david3123123)

## 1. SJY051/mermaid — mermAid

### 어떤 프로젝트인지

한국에 있는 영어 사용자가 로그인 없이 영어로 증상을 말하면, 정부 공공데이터(식약처·심평원·국립중앙의료원 등 공공 API 8종)로 검증된 의약품 정보를 얻고, 지금 열려 있는 근처 약국·병원·응급실을 지도로 찾는 서비스 **mermAid**의 저장소. LG CNS AM 5기 미니 프로젝트 1, 1팀 자유주제 프로젝트. 서비스 이름은 mermAid, 레포 이름은 mermaid.

핵심 원칙: AI는 증상에서 찾을 성분을 정하는 질의까지만 하고, 사용자가 보는 사실은 전부 공공 API에서 온다. 응급 신호는 AI보다 먼저 코드가 잡아 119 안내로 답하고, 알레르기를 선언하면 AI 약 제안은 폐기된다. 모든 응답에 "진단이 아닙니다" 면책이 붙는다.

- 레포: [SJY051/mermaid](https://github.com/SJY051/mermaid) (공개, 기본 브랜치 `main`, 주 언어 Java, 생성 2026-07-10, 최근 활동 2026-07-27, `main` 마지막 커밋 2026-07-16)
- 스택: Spring Boot 3.5 · Java 21 | React 19 · TypeScript · Vite · Tailwind | MariaDB · Redis · 네이버맵, 공공 API 8종 연동
- 구조: `backend/`(Spring Boot, Gradle), `frontend/`(React+TS+Vite), `docs/`, `compose.yaml`, `AGENTS.md`, `.github/`, `.claude/`, `.codex/`

### 전체 활동량

- 커밋 149개 (`main`, 2026-07-10 ~ 07-16)
- PR 90개 (머지 86, 열림 2, 미머지 닫힘 2)
- 이슈 51개 (열림 14, 닫힘 37)
- 기여자별 커밋: SJY051 123개(82.6%), david3123123 13개, GledoubleN 10개, Justgettinby 3개
- 기여자별 PR: SJY051 70개(머지 69), GledoubleN 12개(머지 9, 열림 2), david3123123 5개(전부 머지), Justgettinby 3개(전부 머지)

### 박주형 담당 — FE-2 (지도·저장소)

README 팀 표 기준 역할: **FE-2 지도·저장소**. 팀: 윤서진 리드·BE-1·FE-1 / 임수혁 BE-2(시설 검색) / 박주형 FE-2(지도·저장소) / 최정민 PM·UX·QA.

- 커밋 13개 (2026-07-13 ~ 07-14, 이틀간 집중), 일반 커밋 11개 + 머지 커밋 2개. 백엔드 커밋 0개, 프론트엔드만 작업.
- PR 5개, 전부 머지:
  - #38 `feat(facility): add the detail drawer skeleton` (07-13)
  - #45 `feat(facility): implement the detail drawer (DEV-207)` (07-13)
  - #58 `fix(facility): label fixture data on shared map` (07-13 → 07-14 머지)
  - #63 `feat(facility): add accessible map pins` (07-14)
  - #66 `feat(web): add saved places management` (07-14)
- 주로 만진 파일: `frontend/src/components/FacilityMap.tsx`(8개 커밋), `DetailDrawer.tsx`(6개), `MapScreen.tsx`(3개), `SavedScreen.tsx`·`lib/favorites.tsx`·`lib/storage.ts`(각 1개, #66 저장 장소 관리)
- 한 일: 시설 상세 드로어(DEV-207) 스켈레톤→구현, 접근성 지도 핀, 즐겨찾기(저장 장소) 관리 기능 구현·머지, 지도 마커 타입·응급실 범례 표시 수정, 지도 배경 클릭 시 상세 드로어 닫기, 필터링 시 fixture(가짜 데이터) 안내 문구 유지, 지도 접근성 검토 갭 해소.
- 이슈: 담당 이슈(assignee 지정) 0개, 직접 작성한 이슈 0개. 이 레포는 assignee를 거의 쓰지 않음(51개 중 6개만 지정). 관련 이슈(모두 닫힘): #29 `[온보딩] 박주형 — 첫날 체크리스트`(SJY051 작성), #14 `[DEV-207] 시설 상세 드로어 (UI-03)`, #15 `[DEV-504] 즐겨찾기 저장 UI (C/R/U/D)`, #53 `fix(facility): label fixture data on the shared FacilityMap`.

### 미확인 사항

- GitHub 로그인 ↔ 실명 매핑: 박주형=david3123123만 사용자 확인으로 확정. SJY051=윤서진, GledoubleN=임수혁, Justgettinby=최정민 대응은 README 팀 표와 작업 영역이 일치하는 정황일 뿐 GitHub 데이터만으로 미확정.
- 커밋별 변경 규모(+/- 라인 수), PR additions/deletions: 읽기 도구 집합에 없어 미확인.
- collaborator 목록: 읽기 도구 집합에 없어 미확인.
- `backend/src` 하위 패키지 구조 미확인.
- 최근 업데이트(2026-07-27) 내용: `main` 마지막 커밋이 07-16인데 updated_at이 07-27인 이유(열린 PR #127·#131이나 이슈 활동으로 추정) 미확인.

## 2. SJY051/D3 — D³

### 어떤 프로젝트인지

**D³는 개발자 마이크로블로그(SNS)와 1:1 실시간 경쟁 코딩 배틀을 하나의 성장 경험으로 연결한 플랫폼.** 문제 풀이가 일회성 점수로 끝나면 실력 변화와 개발자 활동이 단절되는데, D³는 풀이와 대전 결과를 공개 피드, 전적, rating·RP로 이어 개발 과정 자체가 정체성과 기록이 되도록 만들었다. 동일 언어 사용자끼리 실시간으로 맞붙고, 서버가 Run·Submit·공격·재접속과 승패를 권위 있게 관리한다. 확정된 결과는 자동으로 커뮤니티에 게시된다.

흐름: 가입·로그인 → 공개 피드 게시·탐색 → 동일 언어 랭크 매칭 → 서버 권위 실시간 배틀(Run·Submit, 공격, 재접속) → 판정·승패 확정 → rating·RP 반영 → 자동 결과 게시·공개 전적.

LG CNS AM 5기 **미니 프로젝트 2** (이슈 #19·#18 라벨 "Mini PJT 2 — 2026-08-20" 기준).

- 레포: [SJY051/D3](https://github.com/SJY051/D3) (공개, 기본 브랜치 `main`, 생성 2026-08-13, 최근 활동 2026-08-19)
- 스택: React · Spring Boot · Judge0 · Kafka · WebSocket · 마이크로서비스 (토픽: competitive-programming, judge0, kafka, microservices, react, spring-boot, websocket)
- 구조: `apps/web`(React), `services/`(Identity·battle·judge·community), `platform/`(Discovery·Config·Gateway), `contracts/`(HTTP·event·WebSocket 계약), `infra/`, `docs/`, `submission/`
- 상태(2026-08-19 기준): 로컬 런타임 동작, P0 골든 패스 로컬 fake judge로 리허설 PASS (회원가입·로그인, Markdown 피드, 동일 언어 매칭, Run·Submit·재접속, 결과·전적, rating·RP 반영, 자동 결과 게시). Surrender 라이브 실증은 NOT RUN, 배포된 judge-service 통합은 NOT RUN.

### 전체 활동량

- 커밋 63개 (`main`, 2026-08-13 ~ 08-19)
- PR 69개 (열림 3, 닫힘 66)
- 이슈 열림 16개 (닫힘 수 미확인 — 페이지 추출에서 확인 못 함)
- 박주형: 커밋 10개, PR 11개(머지 10, 열림 1), 담당 이슈 11개(닫힘 7, 열림 4)

### 박주형 담당 — 웹 프론트엔드 (골든 패스 화면·배틀 WebSocket)

- 커밋 10개 (2026-08-14 ~ 08-19), 전부 웹(`apps/web`)·배틀 영역. 백엔드 서비스 커밋은 없음.
- PR 11개 (머지 10개, 열림 1개):
  - #25 `fix(contracts): normalize validation paths` (08-14, 머지)
  - #28 `feat(web): implement approved P0 golden-path screens` (08-18, 머지)
  - #71 `fix(battle): bound participant WebSocket sessions` (08-18, 머지)
  - #74 `fix(battle): coalesce saturated snapshot resyncs` (08-18, 머지)
  - #79 `feat(battle): seed the deterministic demo problem` (08-18, 머지)
  - #92 `feat(web): polish golden-path visual identity` (08-18, 머지)
  - #89 `fix(web): stabilize battle WebSocket reconnects` (08-19, 머지)
  - #96 `feat(web): surface the self-submission verdict and accepted lock` (08-19, 머지)
  - #101 `feat(web): show author handles in the feed and records` (08-19, 머지)
  - #105 `refactor(web): introduce semantic design tokens` (08-19, 머지)
  - #115 `feat(record): enrich public player records` (08-19, 열림)
- 한 일: P0 골든 패스 화면 구현(#28)과 시각 정체성 다듬기(#92, 시맨틱 디자인 토큰 #105), 배틀 WebSocket 재연결 안정화(#89)·참가자 세션 수 제한(#71)·스냅샷 재동기화 합치기(#74), 시연용 결정적 문제 시드(#79), 제출 판정·accepted lock 표시(#96), 피드·전적에 작성자 핸들 표시(#101), 계약 검증 경로 정규화(#25).
- 담당 이슈 11개 (닫힘 7, 열림 4):
  - 닫힘: #99 피드 게시물 작성자 핸들 계약, #93 와이어프레임·시맨틱 디자인 토큰 기반 시각 시스템 재구축, #84 골든 패스 시각 정체성 다듬기, #82 배틀 화면 제출 판정·accepted lock 표시, #81 로컬 데모 배틀 WebSocket 경로 안정화, #73 버전 관리되는 시연 문제 시드, #39 포화 스냅샷 알림 합치기
  - 열림: #109 전적 전용 화면 + 전적 보강, #37 참가자 WebSocket 세션·인그레스 속도 제한, #19 P0 릴리스 후보 증거·리허설, #18 P0 골든 패스 화면 구현

### 미확인 사항

- 기여자별 커밋 수: 기여자 그래프 페이지가 JS 로딩이라 확인 못 함. 커밋·PR 기준으로는 SJY051과 박주형이 중심.
- 이슈 닫힘 총수: 이슈 목록 추출에서 닫힘 수 확인 못 함.
- 팀원 실명 ↔ GitHub 로그인 매핑: 박주형=david3123123만 확정. SJY051 등 다른 멤버는 미확인.
- 커밋별 변경 규모(+/- 라인 수) 미확인.
