## 프롬프트 유형과 선택 이유
1. [핵심 기반] 3. 역할 부여 (Role-Playing)
- 선택 이유: 이 과제는 단순한 PM이 아닌, 'AI 오케스트레이션'과 'SaaS 비즈니스 모델'을 동시에 이해하는 'AI 프로덕트 아키텍트' 또는 **'시니어 테크니컬 PM'**의 전문성을 요구합니다. AI에게 이 역할을 부여해야, 주니어 PM 수준의 기능 나열이 아닌, 시스템 구조와 ROI를 고려한 명세를 도출할 수 있습니다.

- 효과: "글쓰기 버튼"이 아닌, "개별 에이전트(플롯, 캐릭터, 집필)의 시스템 프롬프트를 사용자가 정의하고, 이들의 실행 순서를 제어하는 오케스트레이션 레이어"와 같은 기술적이고 구체적인 답변을 유도합니다.

2. [논리 엔진] 6. 체인 오브 스루트 (Chain of Thought, CoT)
- 선택 이유: 훈련 초점인 **[구조적 분석 및 세분화]**를 수행하는 핵심 엔진입니다. "장편 소설 AI Agent 메이커"라는 극도로 추상적인 개념을 AI가 스스로 논리적으로 분해하도록 강제합니다.

- 효과: AI가 스스로 '① '메이커'란 무엇인가? (도구) → ② 'AI 오케스트라'란 무엇인가? (기능) → ③ 사용자는 이 도구로 무엇을 하려 하는가? (User Story) → ④ 이를 구현할 시스템은 무엇인가? (기술 명세)'라는 체계적인 사고 과정을 거쳐 결과물을 도출하게 만듭니다.

3. [비즈니스 로직] 8. 조건부 생성 (Conditional)
- 선택 이유: 페르소나의 핵심 성향인 **'최고의 ROI 제안'**을 프롬프트에 명시적인 '조건'으로 주입해야 합니다. 모든 기능 제안은 이 비즈니스 목표를 기준으로 필터링되어야 합니다.

- 효과: AI가 "모든 기능을 다 넣자"가 아닌, **"MVP(최소 기능 제품) 단계에서는 3-Tier (Free, Pro, Enterprise) SaaS 모델을 가정하고, Free 티어에서는 에이전트 1개만, Pro 티어부터 '오케스트레이션' 기능을 제공하여 업셀링을 유도한다"**와 같이 ROI에 기반한 조건부 전략을 생성하게 합니다.

4. [출력 통제] 4. 제약 조건 (Constraint-Based)
- 선택 이유: 개발팀과 디자인팀이 즉시 사용할 수 있는 산출물을 위해, AI의 답변을 Front-end, Back-end, AI/Orchestration, Data 등 명확한 카테고리(목차)로 제어해야 합니다.

- 효과: 산만한 아이디어 나열을 방지하고, 킥오프 미팅에서 즉시 사용할 수 있는 구조화된 '요구사항 명세서(PRD/SRS)' 포맷으로 결과물을 정제합니다.

## 작성 위해 추가 필요 요건
1. 핵심 타겟 유저 (Target User): 이 '메이커'를 사용할 사람은 누구인가? (예: 높은 생산성이 필요한 웹소설 작가, 인디 작가)

2. 핵심 가치 (USP): 이 '메이커'가 다른 AI 글쓰기 툴(예: 뤼튼, 챗GPT)과 다른 점은 무엇인가? (예: '나만의' AI 작가팀(오케스트라)을 직접 구성하고 제어하는 기능)

3. 비즈니스 모델 (ROI): 어떻게 수익을 창출할 것인가? (예: Tiered SaaS 구독 모델)

## 가상 문제 상황
가상 문제 상황 (Scenario Challenge)

페르소나 (Persona): IT 서비스 기획 전문가(PM) AI

성향: 어떠한 아이디어라도 최고의 output을 제공하고, 최고의 ROI에 대한 제안을 합니다.

배경 (Background): AI Agent들이 나오는 시대에서 특정 분야들에 대한 AI 오케스트라가 필요해지고 있습니다.

핵심 문제 (Problem): **"신규 사업: 장편 소설 AI Agent 메이커"**의 사업을 구상. 구체적인 필수 기능 리스트(Feature List), 사용자 흐름(User Flow), 데이터 요구사항이 정의되지 않으면 프로젝트 착수가 무기한 연기될 위기입니다.

해결 과제 (Task): 추상적인 아이디어를 개발자와 디자이너가 즉시 작업할 수 있는 수준의 **'웹 프로토타입 제작을 위한 상세 요구사항 리스트'**로 변환해야 합니다. 기능적 요구사항(회원가입, 식단 입력, 리포트 출력 등)과 비기능적 요구사항(보안, 로딩 속도 등), 그리고 필요한 페이지 구조를 빠짐없이 도출해내야 합니다.

**체계적인 카테고리(Front-end, Back-end, UX/UI 등)**로 나누어 구체화가 필요합니다.

## 문제 해결 프롬프트 
```
[역할 부여]
당신은 Gen-AI SaaS 제품 기획 경험이 풍부한 시니어 프로덕트 매니저(PM)이자 AI 시스템 아키텍트입니다.

[과제 컨텍스트]
신규 사업 아이디어인 "장편 소설 AI Agent 메이커"의 MVP 요구사항 명세서(PRD)를 작성해야 합니다.
이 서비스는 사용자가 '소설 집필'을 위한 여러 AI 에이전트(예: 플롯, 캐릭터, 집필, 교정)를 직접 생성, 설정하고, 이들의 작업 순서(오케스트레이션)를 제어하여 장편 소설의 초안을 완성하는 B2C/B2B SaaS 제품입니다.

[핵심 목표 및 ROI 전략 (Conditional)]
이 프로젝트의 최우선 목표는 '최고의 ROI'입니다. 이를 위해 다음 비즈니스 가정을 전제로 MVP 명세를 작성합니다.
1.  **Target User:** 빠른 생산성이 필요한 웹소설 작가, 인디 작가 ('Prosumer')
2.  **Core USP:** '나만의 AI 작가팀'을 구성하는 커스텀 에이전트 생성 및 워크플로우(오케스트레이션) 편집 기능.
3.  **Business Model:** Tiered SaaS 구독 모델. (MVP는 'Free'와 'Pro' 티어만 가정)
    * `Free Tier:` 에이전트 1개(예: 단순 집필)만 사용 가능. 월 생성 토큰 제한.
    * `Pro Tier:` '오케스트레이션' 기능(핵심 USP) 제공, 다수 에이전트 생성, 더 많은 토큰 제공. **(핵심 업셀링 포인트)**

[핵심 과제 (Instructional + CoT)]
위 [과제 컨텍스트]와 [핵심 목표]를 기반으로, 개발팀과 디자인팀이 즉시 작업에 착수할 수 있는 MVP 웹 프로토타IP의 '상세 요구사항 리스트'를 작성해 주세요.
"AI 오케스트라"라는 추상적인 개념을 '논리적 단계'에 따라 구체적인 기능 명세로 세분화(Breakdown)해야 합니다.

[출력 지침 (Constraint-Based)]
결과물은 반드시 다음의 체계적인 목차(Markdown 형식)를 따라야 합니다.

---
(AI가 생성할 내용 시작)

**제목: 'AI 노블 메이커' MVP 요구사항 명세서 (v0.1) - (ROI Focused)**

**1. 핵심 사용자 Epics 및 MVP User Stories**
* (위 컨텍스트를 기반으로 3~4개의 핵심 User Story를 도출)

**2. 핵심 페이지 구조 (User Flow)**
* (위 User Story를 수행하기 위한 최소한의 페이지 흐름(Flow)을 정의)

**3. 상세 기능 명세 (Structural Breakdown)**

**3-1. UX/UI 및 Front-end 요구사항**
* (예: [공통] 사용자 티어(Free/Pro)에 따른 기능 활성화/비활성화 UI 처리)
* (예: [대시보드] 사용자의 '소설 프로젝트' 리스트)
* (예: [에이전트 메이커 UI] '에이전트'를 생성/편집하는 페이지. (시스템 프롬프트, LLM 모델 선택 등))
* (예: [오케스트라 캔버스] (Pro 전용) '에이전트'들을 노드(Node)처럼 끌어다 놓고 연결하는 워크플로우 에디터 UI (예: React Flow))

**3-2. Back-end / 시스템 요구사항**
* (예: [유저] Stripe 연동 구독 관리 및 JWT 인증)
* (예: [워크플로우] '오케스트라 캔버스'의 노드 연결 정보를 JSON으로 저장하는 API)
* (예: [잡 매니저] 사용자가 '실행' 버튼 클릭 시, 오케스트레이션 워크플로우를 순차적/병렬적으로 실행하는 비동기 작업 큐(Queue) (예: Celery, RabbitMQ))

**3-3. AI / Orchestration 요구사항 (핵심 USP)**
* (예: [에이전트] 사용자가 '시스템 프롬프트', 'LLM 모델'(예: GPT-4o, Claude 3.5), '온도' 등을 설정하는 기능)
* (예: [오케스트레이션] 1번 에이전트(플롯 생성)의 Output을 2번 에이전트(캐릭터 생성)의 Input으로 전달하는 파이프라인 로직)
* (예: [LLM Gateway] 여러 LLM API(OpenAI, Anthropic 등)를 선택/교체할 수 있는 추상화 레이어)

**3-4. 데이터 요구사항 (DB 스키마 예시)**
* (예: `Users` 테이블: `user_id`, `email`, `subscription_tier` ('Free', 'Pro'))
* (예: `Agents` 테이블: `agent_id`, `user_id`, `name`, `system_prompt_template`, `llm_model_id`)
* (예: `Workflows` 테이블: `workflow_id`, `user_id`, `name`, `flow_definition_json` (노드 연결 정보))
* (예: `JobHistory` 테이블: `job_id`, `workflow_id`, `status` ('Pending', 'Running', 'Success'), `output_text_id`)

**4. 비기능적 요구사항 (NFR - ROI 초점)**
* (예: [비용 통제 (ROI)] 사용자별/티어별 API 토큰 사용량 실시간 집계 및 제한(Metering) 기능 (필수))
* (예: [확장성] 비동기 '잡 매니저' 워커(Worker)의 수평적 확장이 가능해야 함.)
* (예: [IP 보호 (보안)] 사용자가 생성한 '에이전트 프롬프트'와 '소설 결과물'은 암호화되어 저장되어야 함.)
```
## 프롬프트 실행 결과

## 프롬프트 실행 결과

(위 프롬프트를 AI가 실행했을 때 생성될 예상 결과물입니다.)

---

**제목: 'AI 노블 메이커' MVP 요구사항 명세서 (v0.1) - (ROI Focused)**

**1. 핵심 사용자 Epics 및 MVP User Stories**

* **Epic 1: AI 작가팀 구성 (핵심 USP)**
    * (Story 1-1) As a Pro User, I want to create a custom 'Character Agent' by defining its role (System Prompt) and model (e.g., Claude 3.5), so I can maintain a consistent character voice.
    * (Story 1-2) As a Pro User, I want to create a 'Plot Agent' that generates outlines based on the 'Save the Cat' structure.
* **Epic 2: 워크플로우 설계 (오케스트레이션)**
    * (Story 2-1) As a Pro User, I want to visually drag and drop my 'Plot Agent' and 'Character Agent' onto a canvas and link them to a 'Drafting Agent', so the drafter uses the output of the first two.
* **Epic 3: 소설 집필 실행**
    * (Story 3-1) As a Pro User, I want to run my workflow and see the AI-generated draft chapter by chapter.
    * (Story 3-2) As a Free User, I want to use a 'Basic Drafting Agent' to write a short scene, so I can test the service before subscribing.
* **Epic 4: 구독 관리 (ROI)**
    * (Story 4-1) As a Free User, I want to be clearly notified when I hit my monthly token limit and be guided to upgrade to the 'Pro' plan.

**2. 핵심 페이지 구조 (User Flow)**

* `P-1: 랜딩/로그인/회원가입` (Pro 플랜 가격 및 기능 소개 포함)
* `P-2: 대시보드 (My Projects)` (사용자가 생성한 '소설 프로젝트' 리스트)
* `P-3: 프로젝트 워크스페이스 (핵심)`
    * `P-3a (Tab 1): 오케스트라 캔버스` (Pro 전용) (시각적 노드 에디터)
    * `P-3b (Tab 2): 내 에이전트 목록` (생성/편집/삭제)
    * `P-3c (Tab 3): 집필 결과물` (생성된 텍스트 초안 뷰어/편집기)
* `P-4: 에이전트 메이커 (모달 or 페이지)` (P-3b에서 호출. 프롬프트, 모델, 파라미터 설정)
* `P-5: 구독 및 결제` (Stripe 연동)

**3. 상세 기능 명세 (Structural Breakdown)**

**3-1. UX/UI 및 Front-end 요구사항**
* **[공통]** `UserContext`를 사용하여 사용자의 `subscription_tier`('Free'/'Pro') 상태를 전역으로 관리.
* **[P-1: 랜딩]** 'Pro' 플랜의 USP('AI 오케스트라') 기능을 시각적으로 강조하는 비교 테이블.
* **[P-3a: 오케스트라 캔버스] (Pro 전용, 핵심)**
    * `React Flow` 또는 유사 라이브러리를 사용한 노드 기반 UI.
    * 좌측 사이드바: `P-3b`의 '내 에이전트 목록'을 드래그앤 드롭 가능.
    * 노드 연결: 노드의 `output` 핸들을 다른 노드의 `input` 핸들로 연결.
    * `Free` 유저에게는 이 탭이 비활성화되고 '업그레이드' 버튼 노출.
* **[P-4: 에이전트 메이커]**
    * 컴포넌트: `Agent Name` (Text input), `System Prompt` (Textarea), `LLM Model` (Dropdown: GPT-4o, Claude 3.5 Sonnet), `Temperature` (Slider 0~1).

**3-2. Back-end / 시스템 요구사항**
* **[유저 (AuthN/AuthZ)]** JWT 기반 인증. `Stripe` 웹훅을 수신하여 `Users` 테이블의 `subscription_tier`를 실시간 업데이트하는 API.
* **[워크플로우]** `P-3a` 캔버스에서 정의된 노드와 연결(Edge) 정보를 `flow_definition_json`으로 저장하는 CRUD API.
* **[잡 매니저 (비동기 처리)]**
    * 사용자가 '워크플로우 실행' 버튼 클릭 시, `JobRequest`를 `RabbitMQ` (또는 SQS) 큐에 전송.
    * `Celery` (또는 K8s Job) 워커가 이 잡을 수신하여 `Orchestration Service`를 트리거.
    * 웹소켓을 통해 Front-end로 실시간 `Job Status` ('Running', 'Step 1/3 Complete'...) 전송.

**3-3. AI / Orchestration 요구사항 (핵심 USP)**
* **[LLM Gateway]** 모든 LLM API 호출을 관리하는 단일 서비스. `X-User-ID` 헤더를 기반으로 `TokenUsage` 테이블에 사용량을 기록 (비용 통제).
* **[Orchestration Service]**
    * `flow_definition_json`을 파싱하여 DAG(방향성 비순환 그래프) 생성.
    * 그래프 순서(예: 1->2->3)에 따라 에이전트(LLM)를 순차적/병렬적으로 호출.
    * `Output Parser:` 1번 에이전트(예: 플롯 생성)의 `output`(텍스트)을 파싱하여 2번 에이전트(예: 집필)의 `input` 프롬프트에 동적으로 주입.

**3-4. 데이터 요구사항 (DB 스키마 예시)**
* `Users`: `user_id` (PK), `email`, `password_hash`, `subscription_tier` (Enum: 'Free', 'Pro'), `stripe_customer_id`
* `Agents`: `agent_id` (PK), `user_id` (FK), `name`, `system_prompt_template` (TEXT), `llm_model_id` (String), `llm_params_json` (예: temp)
* `Workflows`: `workflow_id` (PK), `user_id` (FK), `name`, `flow_definition_json` (JSONB, 노드/엣지 정보)
* `JobHistory`: `job_id` (PK), `workflow_id` (FK), `status` (Enum: 'Pending', 'Success', 'Failed'), `started_at`, `completed_at`
* `TokenUsage`: `usage_id` (PK), `user_id` (FK), `tokens_used`, `cost_usd`, `created_at`

**4. 비기능적 요구사항 (NFR - ROI 초점)**
* **[비용 통제 (ROI)]** (필수) `Free`/`Pro` 티어별 월간 `TokenUsage` 합계가 설정된 임계값(Threshold)을 초과하면, API 호출을 자동으로 차단하고 `LLM Gateway`가 429(Too Many Requests) 에러 반환.
* **[IP 보호 (보안)]** `Agents` 테이블의 `system_prompt_template`과 `JobHistory`의 결과물은 DB 저장 시 암호화(AES-256)되어야 함.
* **[확장성]** `Celery` 워커(AI 잡 처리)는 K8s HPA(수평형 파드 오토스케일러) 또는 Lambda/Cloud Functions를 통해 트래픽에 따라 탄력적으로 확장/축소되어야 함. (유휴 비용 최소화)
* **[유지보수성]** `LLM Gateway`는 새로운 LLM(예: Llama 4)이 출시될 경우, 플러그인(Adapter Pattern) 방식으로 쉽게 추가할 수 있도록 설계.