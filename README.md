<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/banner-dark.svg">
  <img src="./assets/banner-light.svg" width="100%" alt="강동혁 Donghyuk Kang, Builder">
</picture>

<p align="center">
  <a href="mailto:kdhyeok52@gmail.com"><img src="https://img.shields.io/badge/Email-kdhyeok52@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://www.linkedin.com/in/donghyuk-kang-3b7926290/"><img src="https://img.shields.io/badge/LinkedIn-Donghyuk_Kang-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
</p>

<br>

필요한 게 보이면 일단 만들어 보는 편입니다. 캐릭터 AI 채팅 앱을 공동창업해 출시했고, 티켓팅할 때 쓰는 서버시간 조회 서비스를 월 1만 명이 쓰는 서비스로 키웠습니다. 지금은 AI·SW 마에스트로 17기에서 팀을 이끌면서 LLM 모델을 실제 트래픽으로 비교하는 A/B 테스트 게이트웨이를 만들고 있습니다.

만드는 것만큼 실제로 쓰이게 하는 데 시간을 많이 씁니다. 콘서트 현장에서 사용자에게 직접 물어보기도 했고, 고객이 될 만한 팀 30여 곳을 인터뷰하기도 했습니다. 감으로 넘어가지 않으려고 부하 시험도 스무 번 돌렸습니다.

고려대학교 컴퓨터학과에 다니고 있고, 2027년 2월에 졸업합니다.

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/highlights-dark.svg">
  <img src="./assets/highlights-light.svg" width="100%" alt="럭타임 월 사용자 1만 명, AU 출시 첫 주 사용자 2천 명, 고객 후보 30여 팀 인터뷰, 백오피스 7개 통합">
</picture>

<br>

## 만든 것들

### ABTO
**LLM 모델 A/B 테스트 게이트웨이** &nbsp; `2026.04 ~` `팀장` `Go` `Kotlin`

여러 AI 모델을 게이트웨이 하나로 묶고, 실제 트래픽을 모델별로 나눠 어느 쪽이 지표를 더 올리는지 비교합니다. 처음엔 응답 형식을 하나로 맞춰 주는 게 핵심이라고 생각했습니다. 그런데 30여 팀을 만나 보니 다들 원하는 건 "모델을 바꾼 뒤에 뭐가 나아졌는지"에 대한 근거였고, 그래서 게이트웨이의 역할을 트래픽 분기와 지표 수집 쪽으로 다시 잡았습니다.

요청 기록이 하나라도 빠지면 비교 결과가 틀어지는 구조라 유실 없이 받는 게 중요했습니다. 처음 재 봤을 때는 초당 20건에서 이미 기록이 사라지고 있었습니다. 서버부터 늘리는 대신 한 번에 한 조건만 바꾸는 부하 시험을 20회 돌렸습니다.

- 한 줄로 처리되던 전송을 여러 갈래로 나눠 유실률을 0.05%까지 낮췄습니다
- 감당 못 할 요청은 미리 돌려보내게 해서 메모리 초과 재시작을 막았고, 정상 처리량은 오히려 2.45배가 됐습니다
- 이벤트를 20건씩 묶어 받도록 바꿔 초당 134건이던 처리량을 3,000건으로 올렸습니다
- 목표 트래픽을 12분 동안 유지하는 시험을 유실과 재시작 없이 통과했고, 게이트웨이가 더하는 지연은 중앙값 11ms입니다

### 럭타임
**서버시간 조회 서비스** &nbsp; `2025.01 ~ 2025.08` `개발 리드` `MongoDB`

티켓팅처럼 초 단위로 다투는 순간에 쓰는 서비스입니다. 크롤러부터 MongoDB 적재까지 파이프라인을 직접 짰고, 요청이 몰리는 시각을 분석해서 캐싱과 요청 분산만으로 피크 시간 지연을 줄였습니다. 서버는 늘리지 않았습니다. 콘서트 현장에서 사용자들과 이야기해 보니 불안의 원인이 휴대폰 시계였고, 기기 시간 보정 기능을 넣은 뒤 월 사용자 1만 명까지 컸습니다.

### Another Universe
**웹툰, 웹소설 캐릭터와 대화하는 AI 채팅 앱** &nbsp; `2023.09 ~ 2024.06` `공동창업` `React Native` `NestJS` `Azure`

기획부터 앱, 백엔드, LLM 파이프라인, 운영까지 직접 했습니다. 대화가 어색하게 끝난 로그를 모아 분류해 보고 요청을 세 단계로 나눴더니, 캐릭터 답변이 자연스러워지면서 API 비용은 40% 넘게 줄었습니다. 출시 1주 만에 2천 명이 들어왔고 App Store 엔터테인먼트 31위까지 올라갔습니다.
[AnotherUniverseAU](https://github.com/AnotherUniverseAU)

### 공문 자동 분류 프로그램
**OCR 기반 문서 분류** &nbsp; `Python` `OCR`

사회복무요원으로 수어통역센터에서 공문 분류를 맡았을 때 만들었습니다. 매일 3시간씩 손으로 하던 일이었습니다. 도장이나 접힌 자국 때문에 인식이 틀어지는 건 노이즈 제거와 이진화로 잡고, 인식하지 못한 문서는 담당자가 따로 확인하도록 흐름을 나눴습니다. 지금은 15분 정도면 끝납니다.
[Automatic_Document_Classification_Program](https://github.com/cucumber5252/Automatic_Document_Classification_Program)

<br>

## 거쳐 온 곳

| 기간 | 어디서, 무엇을 |
|:--|:--|
| 2026.04 ~ | **AI·SW 마에스트로 17기**<br>3인 팀 팀장으로 ABTO를 만들고 있습니다 |
| 2026.03 ~ | **고려대 데이터과학 및 응용 연구실** 학부연구생<br>멀티모달 순차 추천 연구 1저자. 파라미터를 약 1/200로 줄이면서 성능을 약 45% 높였습니다 (ACM WWW 2027 목표) |
| 2025.08 ~ 2026.02 | **뮌헨공과대학교 (TUM)** 교환학생<br>NLP 연구실 프로젝트에서 서사 유사성 판단 정확도를 0.65에서 0.88로 올렸습니다 |
| 2024.12 ~ 2025.06 | **핀다** 오픈업 Tech팀 풀스택 엔지니어 인턴<br>사내 운영 도구 개발을 전담하며 백오피스 7개를 하나로 합쳤고, 월 2천여 건이던 데이터 정합성 오류를 10건 수준으로 줄였습니다 |
| 2024 | **멋쟁이사자처럼 NEXT 12기** IT창업학회 테크 리드<br>실습 중심 커리큘럼 40회를 기획하고 운영했고, 학회 창업 팀 기술 멘토링을 맡았습니다 |

<br>

## 수상

| 시기 | 내용 |
|:--|:--|
| 2026.07 | KU Silicon Valley 창업 비즈니스 모델 경진대회 **최우수상** (현지 투자자 앞에서 영어로 피칭) |
| 2025.05 | SW중심대학 AI창업경진대회 **기술혁신 특별상** |
| 2023.12 | Startup Express Winter Season **디캠프 창업가상** |
| 2023.11 | Y-deathon 아이디어톤 **장려상** (발표 후 Microsoft Korea에서 컴퓨팅 자원 지원) |

<br>

## 주로 쓰는 것들

| 분야 | 도구 |
|:--|:--|
| Languages | <img src="https://skillicons.dev/icons?i=py,ts,js,go,kotlin,java" height="36"> |
| Backend | <img src="https://skillicons.dev/icons?i=nestjs,express,fastapi,django,flask,spring" height="36"> |
| Frontend, App | <img src="https://skillicons.dev/icons?i=react,nextjs" height="36"> |
| Data | <img src="https://skillicons.dev/icons?i=postgres,mysql,mongodb,redis" height="36"> |
| Infra, Tools | <img src="https://skillicons.dev/icons?i=aws,azure,docker,vercel,git,figma" height="36"> |

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=cucumber5252&theme=github_dark">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=cucumber5252&theme=github" width="100%" alt="GitHub contributions">
</picture>
