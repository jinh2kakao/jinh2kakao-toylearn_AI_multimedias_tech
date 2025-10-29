
### 🚀 Phase 6: 통합 및 운영 (Integration & Operation) 상세 가이드

이 단계는 5가지 핵심 Task로 나뉩니다.

1.  API 통합 및 E2E(End-to-End) 테스트
2.  프로덕션 배포 및 CI/CD 파이프라인 실행
3.  운영 모니터링, 로깅 및 AI 기반 장애 대응
4.  비즈니스 프로세스 자동화 (IpaaS)
5.  AI 기반 피드백 수집 및 다음 사이클(Phase 1) 준비

---

### 1. API 통합 및 E2E(End-to-End) 테스트

* **🎯 목표:** 3단계 프론트엔드에서 사용하던 '가짜(Mock) API'를 4단계에서 개발하고 5단계에서 배포한 '실제(Real) 백엔드 API'로 교체합니다. 또한, 사용자의 시나리오(예: 회원가입 → 로그인 → 프롬프트 저장)가 처음부터 끝까지 정상 작동하는지 E2E 테스트를 수행합니다.
* **🔧 핵심 업무 Task:**
    * 프론트엔드 코드의 API 호출 로직(Service) 수정 (Mock → Real).
    * `fetch` 또는 `axios` 클라이언트의 Base URL 및 인증 헤더(JWT) 설정.
    * 회원가입, 로그인, 프롬프트 생성, 구독 결제 등 핵심 시나리오에 대한 E2E 테스트 스크립트 작성 및 실행.
* **🤖 활용 AI 도구:**
    * **Cursor (AI Native IDE):** 코드베이스 전체(프론트/백엔드)를 이해하며 리팩토링을 지시합니다.
    * **Testim.io, Katalon AI, Playwright (AI):** AI가 UI를 분석하여 E2E 테스트 코드를 자동 생성합니다.
* **💡 AI 활용 전략:**
    * **'맥락' 기반 API 교체:** Cursor AI에게 "4단계의 `@apiSpec.yaml` 파일과 3단계의 `@src/services/api/mockPrompts.ts` 파일을 참조해. `mockPrompts.ts`를 사용하는 모든 프론트엔드 코드를, `apiSpec.yaml`에 정의된 실제 API 엔드포인트를 호출하도록 리팩토링해 줘"라고 지시합니다.
    * **'시나리오' 기반 테스트 생성:** AI 테스트 툴에 "1단계 PRD의 '마케터 김미소' 페르소나의 구독 시나리오를 테스트하는 E2E 스크립트를 생성해 줘"라고 지시합니다.
* **✍️ 예시 프롬프트:**
    > **[API 리팩토링 (Cursor)]**
    > "3단계 프론트엔드 프로젝트(`@Phase-3-Frontend`)의 `src/services/apiClient.ts` 파일을 열어줘.
    > 1.  Base URL을 `process.env.NEXT_PUBLIC_API_URL` (Phase 5에서 설정한 URL)로 설정해.
    > 2.  Zustand 스토어(Phase 3)의 `userToken`을 읽어서, 모든 API 요청의 `Authorization` 헤더에 'Bearer 토큰'을 자동으로 포함하는 `axios` 인터셉터(interceptor)를 추가해 줘.
    > 3.  `fetchPrompts` 함수를 4단계 API(`GET /api/prompts`)에 맞게 수정해 줘."

    > **[E2E 테스트 생성 (Testim.io/Katalon AI)]**
    > "Analyze the 'Sign Up' flow.
    > Generate a test script that:
    > 1.  Navigates to the '/signup' page.
    > 2.  Fills the 'email' and 'password' fields with valid data.
    > 3.  Clicks the 'Sign Up' button.
    > 4.  Asserts that the user is redirected to the '/explore' page.
    > 5.  Asserts that the user's email is visible in the profile menu."

---

### 2. 프로덕션 배포 및 CI/CD 파이프라인 실행

* **🎯 목표:** 5단계에서 준비한 CI/CD 파이프라인(YAML 파일)을 '실행'하여, 1단계에서 통합한 애플리케이션(프론트/백엔드)을 실제 프로덕션(운영) 환경에 배포합니다.
* **🔧 핵심 업무 Task:**
    * `develop` 브랜치(통합 테스트 완료)를 `main` 브랜치로 병합(Merge).
    * Git Push를 통해 GitHub Actions(또는 GitLab CI) 워크플로우를 트리거.
    * CI/CD 대시보드를 모니터링하며 `Test` -> `Build` -> `Deploy` 잡(Job)이 모두 성공하는지 확인.
    * 배포 실패 시 롤백(Rollback) 전략 수행.
* **🤖 활용 AI 도구:**
    * **GitHub Actions, GitLab CI:** (실행 주체) 5단계에서 AI의 도움으로 작성한 파이프라인.
    * **Warp (AI Terminal), GitHub Copilot (in IDE):** Git 명령어 수행을 보조하거나 파이프라인 로그를 자연어로 요약.
* **💡 AI 활용 전략:**
    * **'인간'의 최종 승인:** 이 Task에서 AI는 '실행자'이며, 인간은 '최종 승인자(Orchestrator)'입니다. AI가 구축한 파이프라인을 인간이 'Merge' 버튼을 눌러 실행시킵니다.
    * **AI 기반 로그 분석:** 파이프라인 실패 시, AI 터미널(Warp)에 "방금 실패한 CI/CD 로그를 요약하고 실패 원인을 알려줘"라고 질문합니다.
* **✍️ 예시 프롬프트:**
    > **[파이프라인 로그 요약 (Warp AI)]**
    > (GitHub Actions 로그를 터미널에 스트리밍한 후)
    > "The 'deploy' job just failed. Analyze the logs above and tell me the root cause. Was it an AWS authentication error or a Terraform syntax error?"

    > **[Git 명령어 수행 (Human Task, AI 보조)]**
    > (Copilot 보조를 받으며 터미널에 입력)
    > `git checkout main`
    > `git pull origin main`
    > `git merge develop -m "Deploy: MVP v1.0 Launch (Integrating Frontend and Backend)"`
    > `git push origin main`  *(← 이 명령이 CI/CD 파이프라인을 트리거)*

---

### 3. 운영 모니터링, 로깅 및 AI 기반 장애 대응

* **🎯 목표:** 배포된 라이브 서비스가 안정적으로 작동하는지 '실시간'으로 감시하고, 5단계에서 연동한 AI 모니터링 툴을 활용하여 장애 발생 시 '원인'을 신속하게 파악하고 대응합니다.
* **🔧 핵심 업무 Task:**
    * 모니터링 대시보드(CPU, 메모리, API 응답 시간) 실시간 확인.
    * 에러 트래킹(Sentry)을 확인하여 배포 후 발생하는 신규 에러 식별.
    * AI 모니터링 툴(Datadog Bits AI 등)에 자연어로 '이상 징후' 질문.
* **🤖 활용 AI 도구:**
    * **Datadog (Bits AI), New Relic (GroK):** (핵심) 수집된 방대한 로그와 메트릭을 AI가 분석하여, "왜 느려졌는지", "어떤 에러가 가장 심각한지" 자연어로 답변합니다.
    * **Sentry (AI):** 유사한 에러를 자동으로 그룹화하고, AI가 스택 트레이스를 분석하여 디버깅 힌트를 제공합니다.
* **💡 AI 활용 전략:**
    * **'로그 읽기'에서 '로그 질문하기'로:** 수백만 줄의 로그를 인간이 직접 훑어보는 대신, AI 에이전트에게 "오늘 오후 3시경 `/api/prompts` 엔드포인트에서 발생한 500 에러의 근본 원인(Root Cause)을 요약해 줘"라고 질문합니다.
* **✍️ 예시 프롬프트:**
    > **[장애 원인 분석 (Datadog Bits AI / New Relic GroK)]**
    > "Why did the API latency spike in the `us-east-1` region in the last hour?"
    > (AI 답변 예시: "I noticed a spike in latency correlated with a 40% increase in DB query time for the `SELECT * FROM prompts` query, likely due to a missing index on the `created_at` column.")

    > **[에러 요약 (Sentry AI)]**
    > "Summarize the top 3 new errors that appeared after the 'MVP v1.0 Launch' deployment. Are any of them critical?"

---

### 4. 비즈니스 프로세스 자동화 (IpaaS)

* **🎯 목표:** 4단계의 핵심 백엔드 API와 외부 3rd-party 서비스(예: Stripe 결제, SendGrid 이메일)를 'AI 오케스트레이터(n8n 등)'로 연결하여, 핵심 비즈니스 로직(예: 구독, 알림)을 자동화합니다.
* **🔧 핵심 업무 Task:**
    * (요청하신) `n8n`, `Make.com`, `Zapier` 등을 사용하여 워크플로우 생성.
    * 예: [Stripe 결제 성공 웹훅] → [우리 백엔드 API 호출 (유저 등급 'Pro'로 변경)] → [SendGrid API 호출 (환영 이메일 발송)].
* **🤖 활용 AI 도구:**
    * **n8n (AI 기능), Make.com, Zapier:** 로우코드/노코드(Low-code/No-code) 플랫폼 내의 AI 기능을 활용하여 워크플로우를 자연어로 생성하거나 최적화합니다.
* **💡 AI 활용 전략:**
    * **'접착제(Glue)'로서의 AI:** 핵심 백엔드(Phase 4)는 순수한 API만 제공하고, 자주 바뀌는 비즈니스 정책(예: "Pro 등급 갱신 3일 전 알림 메일 발송")은 `n8n` 같은 AI 기반 자동화 툴에 위임하여 시스템을 유연하게 만듭니다.
* **✍️ 예시 프롬프트:**
    > **[워크플로우 생성 (n8n AI)]**
    > "Create a new workflow based on this prompt:
    > 1.  **Trigger:** When a new webhook is received from `Stripe` with the event `checkout.session.completed`.
    > 2.  **Action 1 (HTTP Request):**
    >     - Extract the `userId` from the webhook's `metadata`.
    >     - Call our production `POST /api/users/{userId}/activate-pro` endpoint. (Use the Bearer Token from Secrets).
    > 3.  **Action 2 (SendGrid):**
    >     - If Action 1 succeeds (status 200).
    >     - Send an email using `SendGrid` to the `customer_email` from the webhook, using the 'Welcome to Pro' template."

---

### 5. AI 기반 피드백 수집 및 다음 사이클(Phase 1) 준비

* **🎯 목표:** '운영' 단계에서 수집된 실제 사용자 데이터와 피드백(로그, 문의, 사용 패턴)을 AI로 분석하여, '다음 개발 사이클(Sprint)'의 **[Phase 1: 기획 및 정의]**를 위한 '데이터 기반 인사이트'를 도출합니다. (프로세스의 순환)
* **🔧 핵심 업무 Task:**
    * 고객센터(Zendesk 등)나 커뮤니티(Discord)에 쌓인 사용자 피드백 수집.
    * 운영 데이터(Datadog 등)를 통한 '가장 많이 사용되는 기능' vs '가장 사용되지 않는 기능' 분석.
    * AI를 활용한 피드백 요약 및 다음 MVP 기능 제안.
* **🤖 활용 AI 도구:**
    * **범용 LLM (Gemini, ChatGPT):** 정성적인(Text) 사용자 피드백을 정량적인 '인사이트'로 요약.
    * **Datadog Bits AI:** 정량적인(Metrics) 사용 패턴을 분석.
* **💡 AI 활용 전략:**
    * **'데이터'에서 '기획'으로:** AI를 단순 장애 대응이 아닌, '프로덕트 매니저(PM)'의 역할로 활용합니다. 수백 개의 고객 문의를 AI에게 요약시켜 다음 스프린트의 우선순위를 정합니다.
* **✍️ 예시 프롬프트:**
    > **[사용자 피드백 분석 (범용 LLM)]**
    > "너는 시니어 프로덕트 매니저(PM) AI야.
    > 아래는 지난 7일간 우리 '프롬프트 라이브러리' 서비스의 고객센터에 접수된 문의 50건의 목록이야.
    > [... (문의 내용 텍스트 붙여넣기) ...]
    >
    > **요청:**
    > 1.  이 피드백들을 '버그 리포트', '기능 제안', '결제 문의' 3가지 카테고리로 분류해 줘.
    > 2.  '기능 제안' 중에서 가장 많이 언급된 요청 3가지를 요약해 줘.
    > 3.  이 데이터를 기반으로, 다음 스프린트(Phase 1)에서 기획할 '사용자 스토리' 1가지를 제안해 줘."

---
