
### 💻 Phase 3: 프론트엔드 개발 (Front-end) 상세 가이드

이 단계는 6가지 핵심 Task로 나뉩니다.

1.  개발 환경 및 프로젝트 설정
2.  디자인-투-코드 (Design-to-Code) 변환
3.  컴포넌트 리팩토링 및 개발
4.  페이지 어셈블리 및 라우팅
5.  상태 관리(State Management) 및 API 연동 (Mock)
6.  인터랙션 및 반응형 구현

---

### 1. 개발 환경 및 프로젝트 설정

* **🎯 목표:** 프론트엔드 프로젝트의 기술 스택(프레임워크, 언어)을 결정하고, AI를 활용하여 초기 설정(Boilerplate)을 신속하게 완료합니다.
* **🔧 핵심 업무 Task:**
    * 프레임워크 선정 (예: React, Next.js, Vue)
    * 프로젝트 초기화 및 폴더 구조 생성
    * 필수 라이브러리 설치 (예: Tailwind CSS, Zustand, Framer Motion)
    * Linter, Formatter 등 개발 표준 설정
* **🤖 활용 AI 도구:**
    * **Cursor (AI Native IDE):** 프로젝트 전체 맥락을 이해하며 초기 설정을 지시합니다.
    * **GitHub Copilot (in VS Code):** `package.json` 등 설정 파일 작성 시 코드를 제안합니다.
    * **범용 LLM (Gemini, ChatGPT):** 최신 기술 스택 조합을 추천받거나 설정 스크립트를 생성합니다.

#### 💡 AI 활용 전략

* **'명령'으로 보일러플레이트 생성:** AI IDE(Cursor)에 자연어로 명령하여, 개발자가 직접 터미널 명령어를 치거나 폴더를 생성하는 시간을 0으로 줄입니다.
* **기술 스택 추천:** AI에게 "우리 서비스(프롬프트 라이브러리)는 SEO가 중요하고, 빠른 로딩이 필요한데 어떤 React 프레임워크가 좋아?"라고 질문하여 Next.js 같은 최적의 스택을 추천받습니다.

#### ✍️ 예시 프롬프트

> **[프로젝트 초기 설정 (Cursor)]**
> "현재 폴더에 'Next.js 14' 프로젝트를 'TypeScript' 기반으로 새로 생성해 줘.
> 스타일링은 'Tailwind CSS'를 사용할 거야.
> 추가로 'Zustand' (상태관리), 'Axios' (API 통신), 'Framer Motion' (애니메이션) 라이브러리를 설치해 줘.
> 마지막으로, `src/components`, `src/app`, `src/store`, `src/services` 폴더 구조를 자동으로 생성해 줘."

---

### 2. 디자인-투-코드 (Design-to-Code) 변환

* **🎯 목표:** 2단계의 Figma 목업 이미지를 AI 도구에 입력하여, 기본 HTML/CSS (React/Vue) 코드의 초안(70~80%)을 즉시 생성합니다.
* **🔧 핵심 업무 Task:**
    * Figma 디자인 시안(Explore Page, Pro Card 등)을 이미지로 export 하거나 Figma 링크 준비
    * AI Design-to-Code 툴을 활용하여 1차 코드 생성
* **🤖 활용 AI 도구:**
    * **v0.dev (Vercel):** (강력 추천) 이미지나 프롬프트를 기반으로 React + Tailwind 컴포넌트 코드를 실시간으로 생성하고 수정합니다.
    * **Locofy.ai, Anima:** Figma 플러그인 형태로 작동하며, Figma의 Auto-Layout과 컴포넌트를 분석하여 코드로 변환합니다.
    * **Galileo AI, Uizard:** 2단계에서 사용했던 툴이 Hi-Fi 목업과 동시에 코드도 함께 export 해줍니다.

#### 💡 AI 활용 전략

* **'완벽함'이 아닌 '초안'으로 활용:** AI가 생성한 코드는 완벽하지 않습니다. 스타일(CSS)과 구조(HTML)를 빠르게 복사해오는 '초안'으로 사용하고, 로직은 3단계에서 직접(AI와 함께) 수정합니다.
* **'컴포넌트' 단위로 변환:** 페이지 전체를 한 번에 변환하기보다, 2단계의 디자인 시스템에 정의된 'Prompt Card', 'LNB', 'Button' 등 핵심 컴포넌트 단위로 변환하는 것이 코드 품질이 더 높습니다.

#### ✍️ 예시 프롬프트

> **[컴포넌트 생성 (v0.dev)]**
> (2단계에서 만든 'Prompt Card' UI 목업 이미지를 업로드하며)
> "Create a React component based on this image.
> It must be a card with a 'Glassmorphism' background.
> It should have a small 'PRO' badge in the top-right corner.
> The preview text at the bottom should be slightly blurred.
> Use Tailwind CSS for all styling."

> **[Figma 플러그인 (Locofy.ai)]**
> (Figma 내에서 'Explore Page' 프레임을 선택한 상태)
> "Sync this frame to a new React + TypeScript project.
> Maintain all responsive constraints set in Figma.
> Automatically detect and create components for 'PromptCard' and 'NavBar'."

---

### 3. 컴포넌트 리팩토링 및 개발

* **🎯 목표:** 2단계에서 생성된 '날것(raw)'의 코드를 가져와, 실제 데이터를 받을 수 있도록 'props'를 정의하고, '상태(state)'를 추가하여 재사용 가능한 컴포넌트로 리팩토링합니다.
* **🔧 핵심 업무 Task:**
    * 정적(static) HTML을 동적(dynamic) 컴포넌트로 변환
    * 컴포넌트가 받아야 할 Props 정의 (예:LNB는 isExpanded 상태를 가져야 함)
    * Storybook 등을 활용한 컴포넌트 문서화
* **🤖 활용 AI 도구:**
    * Cursor (AI Native IDE): (핵심) 코드베이스 전체를 이해하는 AI 에디터. "이 코드 리팩토링해줘"라는 자연어 명령으로 개발의 80%를 수행합니다.
    * GitHub Copilot / Copilot Chat: IDE 내에서 실시간으로 코드 완성 및 리팩토링 제안.
* **💡 AI 활용 전략:**
    * '맥락(Context)' 기반 리팩토링: Cursor는 열려있는 모든 파일과 코드베이스를 '맥락'으로 이해합니다. "이 PromptCard 컴포넌트 리팩토링해줘. Props는 types/prompt.ts 파일에 정의된 Prompt 타입을 참조해서 자동으로 설정해 줘"와 같이 코드베이스 전체를 활용하는 명령이 가능합니다.
    * '가르치면서' 개발: (Cursor) @ 기호를 사용하여 특정 파일(예: @src/design-system.ts)을 AI의 맥락에 명시적으로 포함시켜, "이 디자인 시스템의 변수를 사용해서 버튼을 다시 스타일링해줘"라고 지시할 수 있습니다.
* **✍️ 예시 프롬프트:**
    * [컴포넌트 리팩토링 (Cursor)] (v0.dev가 생성한 PromptCard.tsx 파일을 연 상태) "Refactor this component.
    1. It should accept props based on the Prompt interface (find it in src/types/prompt.ts).
    2. The props are: title: string, description: string, agentType: string, isPro: boolean.
    3. Use the isPro prop to conditionally show the 'PRO' badge and apply the text blur.
    4. Add a hover effect: the card should gently scale up (103%) using framer-motion."

---

### 4. 페이지 어셈블리 및 라우팅

* **🎯 목표:** 3단계에서 개발한 개별 컴포넌트들을 2단계의 UI 목업 레이아웃대로 조립하여, 실제 페이지(화면)를 완성하고 페이지 간 이동(라우팅)을 구현합니다.
* **🔧 핵심 업무 Task:**
    * 페이지별 라우트(Route) 설정 (예: `app/page.tsx`, `app/library/page.tsx`)
    * 공통 레이아웃(LNB, TopBar 포함) 생성
    * 각 페이지에 필요한 컴포넌트들을 배치
* **🤖 활용 AI 도구:**
    * **Cursor, GitHub Copilot:** 파일 생성 및 컴포넌트 import/배치 작업 자동화.

#### 💡 AI 활용 전략

* **'구조'를 명령:** AI에게 컴포넌트를 조립하는 상위 페이지의 구조를 자연어로 지시합니다.

#### ✍️ 예시 프롬프트

> **[페이지 라우팅 및 생성 (Cursor)]**
> "Create the file-based routing structure in the `src/app` directory based on our (Phase 1) PRD.
> I need:
> - `/` (for the 'Explore' page)
> - `/library` (for 'My Library')
> - `/suggest` (for 'Suggestions')
> - `/settings`
>
> Create a `layout.tsx` file that includes our `LNB` and `TopBar` components, so they are shared across all pages."

> **[페이지 조립 (Cursor)]**
> (새로 만든 `app/page.tsx` (Explore 페이지) 파일)
> "Build the 'Explore' page.
> 1.  Import the `SearchBar` component at the top.
> 2.  Import the `FilterTabs` component below the search bar.
> 3.  Below that, create the masonry grid layout (using CSS Grid or a library).
> 4.  Inside the grid, fetch (mock) data and render a list of `PromptCard` components by mapping over the data."


---

### 5. 상태 관리(State Management) 및 API 연동 (Mock)

* **🎯 목표:** 사용자 정보(로그인 상태), UI 상태(LNB 확장 여부) 등을 전역적으로 관리할 '상태 관리' 스토어를 구축하고, 백엔드(Phase 4)가 완성되기 전까지 '가짜(Mock) API'를 연동하여 개발을 지속합니다.
* **🔧 핵심 업무 Task:**
    * 전역 상태 관리 스토어(Zustand, Redux 등) 설정
    * 로그인, 사용자 정보, UI 상태(LNB 등)를 스토어에 추가
    * 백엔드 API 명세서(Phase 4에서 정의)를 기반으로 Mock API 서비스 생성
    * 페이지에서 Mock API를 호출하여 데이터가 정상적으로 표시되는지 확인
* **🤖 활용 AI 도구:**
    * **Cursor, GitHub Copilot:** 상태 관리 스토어의 보일러플레이트 코드, Mock API 데이터 및 함수를 신속하게 생성합니다.
    * **범용 LLM:** 복잡한 상태 관리 로직(예: Optimistic UI Update)에 대한 패턴을 질문하고 코드를 얻습니다.

#### 💡 AI 활용 전략

* **Mock Data 생성 자동화:** AI는 대량의 '그럴듯한' 가짜 데이터를 즉시 생성할 수 있습니다.
* **API 함수 자동 생성:** API 명세(예: "GET /api/prompts")만 알려주면, AI가 `axios`를 사용한 비동기 fetch 함수를 자동으로 작성해 줍니다.

#### ✍️ 예시 프롬프트

> **[상태 관리 스토어 생성 (Cursor)]**
> "Create a new Zustand store in `src/store/ui.ts`.
> This store should manage the global UI state.
> It needs:
> 1. `isLNBExpanded: boolean` (default: false)
> 2. `toggleLNB: () => void` (a function to toggle the boolean)"

> **[Mock API 생성 (Cursor)]**
> "Create a new file `src/services/api/mockPrompts.ts`.
> 1.  Define a `Prompt` type (use the one from `src/types/prompt.ts`).
> 2.  Create a mock data array (`MOCK_PROMPTS`) containing 20 realistic `Prompt` objects (use varied data).
> 3.  Create an async function `fetchPrompts(page: number, limit: number = 10)` that returns a Promise resolving with a paginated slice of the `MOCK_PROMPTS` array after a 300ms delay."

---

### 6. 인터랙션 및 반응형 구현

* **🎯 목표:** 2단계에서 정의한 애니메이션, 호버 효과 등을 실제 코드로 구현하고, 데스크톱, 태블릿, 모바일 환경에서 UI가 깨지지 않도록 반응형 디자인을 완성합니다.
* **🔧 핵심 업무 Task:**
    * Framer Motion 등을 사용한 미세 인터랙션(Micro-interaction) 추가
    * LNB 확장/축소 애니메이션 구현
    * Tailwind CSS의 반응형 분기점(`sm:`, `md:`, `lg:`)을 사용하여 모바일/태블릿 레이아웃 최적화
* **🤖 활용 AI 도구:**
    * **Cursor, GitHub Copilot:** 애니메이션 라이브러리 코드 작성, 반응형 CSS 클래스 추가.
    * **Framer Motion (AI):** (Framer 사용 시) AI가 인터랙션을 자동 제안.

#### 💡 AI 활용 전략

* **'디버깅'에 AI 활용:** AI에게 "이 컴포넌트가 모바일에서 깨져 보여. Tailwind CSS 코드를 수정해 줘"라고 지시하여 반응형 디버깅 시간을 단축합니다.
* **복잡한 애니메이션 코드 생성:** "Framer Motion을 사용해서 LNB가 부드럽게(ease-out) 0.3초 동안 확장되는 코드를 작성해 줘."

#### ✍️ 예시 프롬프트

> **[반응형 수정 (Cursor)]**
> (Explore 페이지의 Masonry Grid 코드를 선택한 상태)
> "Review this grid layout's Tailwind CSS classes.
> It needs to be responsive:
> - 1 column on mobile (default)
> - 2 columns on tablet (md: breakpoint)
> - 4 columns on desktop (lg: breakpoint)
> Apply the correct `grid-cols-` classes."

> **[애니메이션 추가 (Cursor)]**
> (PromptCard.tsx 파일)
> "Wrap this card component with `motion.div` from `framer-motion`.
> Add an animation: when the component appears on screen (whileInView), it should fade in and slide up slightly from the bottom (e.t., `y: 20`, `opacity: 0` to `y: 0`, `opacity: 1`)."

---

이 3단계가 완료되면, 우리는 2단계의 '시각적 디자인'을 **[상호작용 가능한 프론트엔드 애플리케이션 (Mock API 연동 상태)]**이라는 기능적 산출물로 변환했습니다.

이 산출물은 다음 단계인 **[Phase 4: 백엔드 개발]**의 AI 에이전트가 개발할 실제 API를 기다리는 상태가 됩니다.

다음으로 Phase 4(백엔드 개발) 단계의 상세 가이드가 필요하시면 말씀해 주십시오.