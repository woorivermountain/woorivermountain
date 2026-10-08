<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/profile-banner-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/profile-banner-light.svg">
  <img alt="AI가 없었다면, 어떻게 풀었을까요? 우강산 · Kang-San Woo" src="./assets/profile-banner-light.svg" width="100%">
</picture>

# Kang-San Woo · 우강산 (Kevin) (Kevin)

**UOU Undergraduate · Philosophy & Counseling + Industrial Management Engineering**

SKALA 4기에서 프로젝트를 통해 AI를 배우고 있습니다.

제한된 자원 안에서 쓸 수 있는 해결책을 만듭니다. 먼저 AI 없이도 문제를 풀 수 있는지 살피고, 사용자 업무에서 AI가 필요한 지점과 확인할 기준을 정합니다. Python과 TypeScript로 근거 검색, LLM 업무 흐름과 평가 코드를 구현합니다.

팀장으로 프로젝트를 진행하며 기능을 나누는 것만큼 각자의 맥락을 맞추는 일이 중요하다고 느꼈습니다. 요구사항을 설명하고, 회의에서 합의하고, 다시 만드는 데 드는 비용을 줄이면 제품도 더 빠르게 발전할 수 있다고 생각합니다.

[대표 프로젝트](#대표-프로젝트) · [팀을 이끈 경험](#팀을-이끈-경험) · [지금 고민하는 것](#지금-고민하는-것) · [LinkedIn](https://www.linkedin.com/in/kang-san-woo-1a8511435/)

## 대표 프로젝트

### 골든타임 — 인터뷰에서 근거 검색까지

산재 조사에서 필요한 것은 자료를 찾고 대조할 수 있는 출발점이었습니다. **5인 팀장·PM·개발**을 맡아 실무자 인터뷰로 문제를 좁히고, 질병군 분류·판정례 검색·사실관계 타임라인을 Python 웹 프로토타입으로 연결했습니다. 최종 판단은 조사자가 내리도록 설계했습니다.

[프로젝트와 실행 방법](https://github.com/woorivermountain/goldentime) · [검색·분류 평가](https://github.com/woorivermountain/goldentime/blob/main/docs/EVALUATION.md)

<details>
<summary>골든타임의 데이터와 평가 조건 보기</summary>

공개 판정례 56,535건을 검색 기반으로 구성했습니다. 질병 분류 1,253건에서는 Top-3 79%를 보고했습니다. 검색은 140개 질의마다 후보 120건을 둔 Known-item 평가에서 Hit@10 77.9%, MRR 0.521을 얻었습니다.

현재 질의 흐름은 규칙 기반 분류와 근거 검색입니다. 검색 결과를 생성 모델에 넣는 RAG와 구분합니다. 이 평가는 실제 조사 시간 단축이나 판정 정확도 향상을 측정한 결과가 아니며, 질병군별 편차는 평가 문서에 남겼습니다.

</details>

### 산업 검사 데이터 감사 — 학습 전에 데이터부터

제공된 검사 데이터가 무엇을 보여주는지부터 확인했습니다. DaiS Lab의 일경험 과제에서는 판정 후 그려진 테두리가 정답을 드러내는 경로를 추적했습니다. 이후 공개 Siemens 데이터로 평가를 확장해 분류 점수, 시간 구간과 검사량 절감 목표를 함께 살폈고, 목표를 충족하지 못한 결과는 적용 보류의 근거로 남겼습니다.

[연구 흐름과 산출물](https://github.com/woorivermountain/inspection-data-audit) · [계산 조건과 증거 원장](https://github.com/woorivermountain/inspection-data-audit/tree/main/inspection_data_audit/outputs)

<details>
<summary>현장 과제와 공개 데이터 확장 평가 구분해서 보기</summary>

현장 과제에서는 검사 로그 7,800건과 이미지 364장의 생성 과정을 검토하고 2,000회 치환 검정을 수행했습니다. 표본이 충분하다고 결론 내리지 않고 추가 수집·재검증 조건을 제안했습니다.

별도의 공개 Siemens SMT AOI 데이터 440,274행에서는 calibration에서 고정한 임계값으로 미래 전체 AUROC 0.878, 결함 누락 0.85%, 검사량 절감 3.16%를 보고했습니다. calibration부터 절감 목표 40%에 미달했으며, 마지막 미래 구간의 결함 누락은 1.39%였습니다. 실제 공장에 적용해 얻은 운영 성과는 아닙니다.

</details>

### 모이다 · Meeting Copilot — 회의의 합의를 다음 행동으로

회의에서 결정한 내용이 다음 행동으로 이어지도록 공유 워크스페이스를 만들었습니다. 필요할 때 AI를 호출하고, 제안된 결정·담당자·미결 쟁점을 검토한 뒤 승인하는 흐름입니다. 제품 흐름, Nuxt 화면, 서버 API와 평가 코드를 구현했으며, 인용문 출처와 담당자 명단을 확인한 뒤 승인된 결정·할 일만 DB에 저장합니다.

[제품 흐름과 실행 방법](https://github.com/woorivermountain/meeting-copilot) · [출력 검증과 평가](https://github.com/woorivermountain/meeting-copilot/blob/main/docs/EVALUATION.md)

<details>
<summary>Meeting Copilot에서 테스트한 것과 다음 과제 보기</summary>

외부 모델을 호출하지 않는 결정론적 provider를 사용해 경계 테스트 12/12, 전체 회귀 테스트 20/20을 보고했습니다. 인용문이 원문에 있는지, 담당자가 명단에 있는지, 일반 발화를 AI 요청으로 처리하는지 등을 검사합니다.

고정 테스트 통과는 실제 모델의 답변 정확도 100%를 뜻하지 않습니다. 실제 회의에서의 제안 품질, 사용자의 수정 과정, 호출 비용과 지연은 다음 평가 과제입니다.

</details>

## 팀을 이끈 경험

**자동차 혼류라인 · 캡스톤 팀장** — 파워트레인별 생산로그를 다시 나누고 EDA·ANOVA와 Siemens Plant Simulation으로 투입 순서 개선안을 비교했습니다. 시뮬레이션에서 부하 편차 20% 감소와 가동률 5.1%p 향상 가능성을 확인했고, 실제 공장 적용 결과와 구분해 설명했습니다. 2025년 12월 캡스톤디자인 우수상을 받았습니다.

**골든타임 · 5인 팀장** — 자동판정과 가이드라인 사이에서 나뉜 의견을 현업의 자료 검색·대조 문제로 모았습니다. 문제 정의, 시스템 구조, 핵심 구현과 평가 설계를 연결했고, 2026년 6월 공공 빅데이터·AI 실전 문제 해결 경진대회 대상과 7월 울산 공공데이터·AI 창업경진대회 우수상을 팀으로 받았습니다.

**동행 · 부울경 해커톤 4인 팀장** — 시니어의 외출 계획부터 이동 중 재계획, 자녀 리포트까지 한 사용자 여정을 정했습니다. 5개 Agent와 부모·자녀 화면의 입력·출력·예외 조건을 맞춰 무박 2일의 시연 흐름을 통합했고, 2026년 7월 일반부 우수상을 받았습니다. [통합 과정과 이후의 변화 읽기](./case-studies/bukyeong-multi-agent.md)

## 더 살펴볼 프로젝트

<details>
<summary>배터리 예측·날씨 인터페이스·안전 흐름·학습 도구 보기</summary>

**[ESS 배터리 수명 예측](https://github.com/woorivermountain/ess-battery-life)** — 실험실 LFP 셀 데이터로 초기 충·방전 정보가 수명 예측에 얼마나 도움이 되는지 살폈습니다. Batch 1에서 모델을 선택하고 Batch 2를 고정 평가로 남겼습니다. CV MAPE 7.49%와 외부 Batch MAPE 26.59%를 함께 보고하며, 결과를 본 뒤 더 좋아 보이는 모델로 교체하지 않았습니다.

**[SKY NOW](https://github.com/woorivermountain/sky-now)** — 출처와 갱신 상태를 확인할 수 있는 날씨 인터페이스입니다. 지역별 데이터를 정규화하고, 캐시 상태와 화면 밖 애니메이션의 동작을 다뤘습니다.

**[Smart Safety Helmet](https://github.com/woorivermountain/smart-safety-helmet)** — 위험 알림에서 사람의 확인·취소로 이어지는 흐름을 React·TypeScript로 구현했습니다. 센서·모델·응급 연동은 Mock으로 구성한 프로토타입입니다.

**[SKALA 학습 플래너](https://github.com/woorivermountain/skala-study-planner)** — 교육 일정과 복습 항목을 정리하는 학습 도구입니다. 학습 과정에서 필요한 작은 기능도 직접 구현하며 기록합니다.

</details>

## 지금 고민하는 것

울산대학교에서 철학상담학과와 산업경영공학부를 복수전공해 왔고, 현재 휴학 중입니다. DaiS Lab 학부연구생으로 제조 데이터와 숙련자의 판단을 배우며, SKALA 4기에서 LLM·RAG·Agent·MLOps를 학습하고 있습니다.

요즘은 도메인을 배울 때 무엇부터 확인해야 하는지 기준을 세우고 있습니다. 누가 어떤 정보를 보고 판단하는지, 데이터는 어느 시점에 만들어지는지, 틀렸을 때 누가 다시 확인하는지부터 질문합니다. AI를 도입할 때도 모델 호출 비용과 함께 설명·합의·재작업에 드는 전체 비용을 살피려 합니다.

이 질문과 프로젝트에서 바꾼 선택을 [LinkedIn](https://www.linkedin.com/in/kang-san-woo-1a8511435/)에 이어서 기록하겠습니다.
