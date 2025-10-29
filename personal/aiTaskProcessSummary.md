
### 🤖 AI 에이전트 및 웹 프로덕트 기반 상세 개발 프로세스

각 단계별 AI 에이전트(역할)와 이를 수행할 수 있는 구체적인 상용 웹 프로덕트/도구들입니다.

| 단계 (Phase) | 핵심 AI 에이전트 (역할) | 주요 AI 웹 프로덕트 (도구) | 링크 |
| :--- | :--- | :--- | :--- |
| **1. 기획 및 정의** | 1. **PM AI** <br> 2. **UX 리서처 AI** <br> 3. **데이터 분석가 AI** | - **범용 LLM (Gemini, ChatGPT-4o, Claude 3):** 시장 조사, 경쟁 분석, 페르소나 정의, PRD(제품 요구사항 명세서) 초안 작성 <br> - **Figma (FigJam AI), Miro AI:** AI 기반 브레인스토밍, 사용자 여정 맵(User Journey Map) 및 다이어그램 자동 생성 <br> - **Gamma, Tome:** 기획안 및 IR 자료용 AI 프레젠테이션 자동 생성 | [링크](./process/01_UIUXplanning.md) |
| **2. UI/UX 디자인** | 1. **UI/UX 디자이너 AI** <br> 2. **그래픽 디자이너 AI** <br> 3. **프롬프트 엔지니어 (Human)** | - **Midjourney, DALL-E 3, Lovart AI:** (요청) 서비스 무드보드, 핵심 비주얼, 아이콘 및 로고 컨셉 생성 <br> - **Galileo AI, Uizard:** 텍스트 프롬프트 또는 와이어프레임을 고품질(Hi-Fi) UI 목업으로 즉시 변환 <br> - **Figma AI (Make Designs):** (요청) 기존 디자인 시스템을 기반으로 새로운 화면이나 컴포넌트를 자동 생성 및 반복 수정 <br> - **Spline AI:** 웹용 인터랙티브 3D 에셋 생성 | [링크](./process/02_UIUXdesign.md) |
| **3. 프론트엔드** | 1. **프론트엔드 개발자 AI** <br> 2. **UI 인터랙션 엔지니어 AI** | - **Cursor:** (요청) AI 네이티브 코드 에디터. 코드베이스 전체를 이해하며 UI 컴포넌트 생성, 리팩토링, 디버깅을 지시 <br> - **v0.dev (Vercel), Builder.io:** 프롬프트 또는 디자인 시안을 기반으로 React/Tailwind 컴포넌트 코드 즉시 생성 <br> - **Locofy.ai, Anima:** Figma/Adobe XD 디자인을 프로덕션 수준의 반응형 코드로 변환 <br> - **GitHub Copilot, Replit AI:** IDE 내에서의 코드 자동 완성 및 로직 구현 보조 | [링크](./process/03_frontEnd.md) |
| **4. 백엔드** | 1. **백엔드 개발자 AI** <br> 2. **QA 엔지니어 AI** <br> 3. **API 아키텍트 AI** | - **Cursor:** (요청) AI 에디터 내에서 API 엔드포인트, 비즈니스 로직, 데이터 모델 코드 생성 및 리팩토링 지시 <br> - **GitHub Copilot, Amazon CodeWhisperer:** 보일러플레이트 코드, API 로직, 알고리즘 구현 보조 <br> - **CodiumAI, Tabnine:** 생성된 코드에 대한 단위 테스트(Unit Test) 케이스 자동 생성 및 코드 품질 검증 <br> - **Mintlify, Scribe:** 코드베이스를 분석하여 API 문서를 자동으로 생성 및 업데이트 | [링크](./process/04_backEnd.md) |
| **5. DB 및 인프라** | 1. **DBA (데이터베이스 관리자) AI** <br> 2. **DevOps 엔지니어 AI** <br> 3. **클라우드 아키텍트 AI** | - **범용 LLM (Gemini, Claude 3):** 서비스 요구사항에 맞는 SQL/NoSQL 스키마 설계, 복잡한 쿼리 생성 <br> - **GitHub Copilot (in VS Code):** Dockerfile, Terraform, k8s 설정 파일(IaC) 등 인프라 코드 작성 지원 <br> - **Warp, Fig (Amazon):** AI 기반 터미널. 자연어 명령을 실제 Shell 명령어로 번역 및 실행 <br> - **Brev.dev, Mutable.ai:** AI가 개발 환경을 자동으로 구성하거나, 레거시 코드를 현대적 인프라에 맞게 리팩토링 | [링크](./process/05_dbInfra.md) |
| **6. 통합 및 운영** | 1. **오토메이션 스페셜리스트 AI** <br> 2. **SRE (사이트 신뢰성) AI** <br> 3. **QA 오토메이션 AI** | - **n8n, Make.com, Zapier:** (요청) AI가 생성한 여러 API와 외부 서비스(Stripe, SendGrid 등)를 연결하는 워크플로우 자동화 (IpaaS) <br> - **Datadog (Bits AI), New Relic (GroK):** AI가 로그 및 메트릭을 실시간 분석하여 이상 징후 탐지 및 문제 원인 추론 <br> - **Testim.io, Katalon AI:** AI가 UI를 분석하여 E2E(End-to-End) 테스트 스크립트를 자동으로 생성 및 유지보수 | [링크](./process/06_devOps.md) |

---

### 💡 중요: AI 오케스트레이터(Orchestrator) 및 플랫폼의 역할

요청하신 `Cursor`와 `n8n`은 이 프로세스에서 특히 중요한 **'오케스트레이터(지휘자)'** 역할을 합니다.

1.  **개발 오케스트레이터 (Development Orchestrator) - `Cursor`**
    * 기존의 `GitHub Copilot`이 '보조' 역할이었다면, `Cursor`는 '지휘' 역할에 가깝습니다.
    * 개발자가 "내 코드베이스 전체를 읽고, '프롬프트 라이브러리'에 '태그' 기능을 추가해 줘. 필요한 API, DB 스키마 변경, 프론트엔드 UI 컴포넌트까지 모두 수정해 줘."라고 지시할 수 있습니다.
    * 즉, 여러 AI 에이전트(Front, Back, DB)가 해야 할 일을 하나의 에디터 환경에서 인간이 지휘하는 것입니다.

2.  **프로세스 오케스트레이터 (Process Orchestrator) - `n8n` / `Make.com`**
    * AI가 각자 생성한 기능(API)들은 결국 서로 연결되어야 합니다.
    * `n8n` 같은 도구는 "사용자가 'Upgrade to Pro' 버튼을 누르면(Front-end) -> Stripe API로 결제를 처리하고(Back-end) -> DB의 사용자 등급을 'Pro'로 업데이트한 뒤(DB) -> '환영 메일'을 발송(External API)하라"와 같은 비즈니스 로직 자체를 자동화하고 연결하는 '접착제' 역할을 AI 기반으로 수행합니다.

이처럼 AI 네이티브 개발은 단순히 개별 AI 도구를 사용하는 것을 넘어, **AI가 AI를 지휘하고 연결하는 플랫폼**을 활용하는 방향으로 발전하고 있습니다.