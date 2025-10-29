
### 🎨 Phase 2: UI/UX 디자인 (Design) 상세 가이드

이 단계는 4가지 핵심 Task로 나뉩니다.

1.  무드보드 및 비주얼 컨셉 확립
2.  와이어프레임(Lo-Fi) 및 사용자 플로우(Flow) 설계
3.  고품질(Hi-Fi) UI 목업 생성
4.  디자인 시스템 및 컴포넌트화

---

### 1. 무드보드 및 비주얼 컨셉 확립

* **🎯 목표:** 서비스의 전반적인 '느낌과 분위기(Look and Feel)'를 정의합니다. PRD의 키워드(예: "전문적", "AI", "라이브러리")를 시각 언어(색상, 타이포그래피, 스타일)로 번역합니다.
* **🔧 핵심 업무 Task:**
    * 핵심 키워드 도출 (1단계 PRD에서 가져옴)
    * 메인 컬러 팔레트 (Primary, Secondary, Accent) 정의
    * 타이포그래피(글꼴) 시스템 정의
    * 로고 및 아이콘 스타일 컨셉 생성
* **🤖 활용 AI 도구:**
    * **Midjourney, Lovart AI:** 무드보드, 비주얼 컨셉, 영감을 주는 이미지 생성에 탁월합니다.
    * **DALL-E 3 (in ChatGPT):** 로고, 아이콘 등 구체적인 그래픽 에셋 생성에 유용합니다.
    * **Adobe Firefly:** 텍스트 이펙트나 로고 컨셉 생성에 강점이 있습니다.

#### 💡 AI 활용 전략

* **'키워드'에서 '스타일'로:** 1단계에서 정의한 `전문적`, `다크 모드`, `데이터 중심`, `미래적` 등의 키워드를 AI 프롬프트에 직접 주입하여 시각적 일관성을 확보합니다.
* **영감(Inspiration)으로 활용:** AI가 생성한 이미지를 그대로 쓰기보다, 해당 이미지의 '스타일', '색감', '레이아웃'을 차용하여 디자이너(혹은 인간 오케스트레이터)가 Figma에서 재구성합니다.

#### ✍️ 예시 프롬프트

> **[무드보드 생성 프롬프트 (Midjourney/Lovart AI)]**
> "UI/UX moodboard for a 'Prompt Library' subscription service.
> Keywords: professional, futuristic, data-rich, dark mode.
> The aesthetic is 'Glassmorphism' combined with a 'Masonry Grid' layout.
> Color Palette: Deep charcoal gray background, with vibrant 'intelligent blue' and 'magenta' as accent colors.
> This should look like a high-tech dashboard. --ar 16:9"

> **[로고/아이콘 컨셉 프롬프트 (DALL-E 3)]**
> "A minimalist logo concept for a service named 'AgentLib'. The logo must be a clean, vector icon. It should combine the shape of a 'brain' (representing AI agents) and a 'book' or 'layers' (representing a library). White icon on a $#1E1E24$ dark background."

---

### 2. 와이어프레임(Lo-Fi) 및 사용자 플로우(Flow) 설계

* **🎯 목표:** 1단계의 '사용자 스토리(User Stories)'를 실제 화면의 '뼈대(Wireframe)'로 변환합니다. 색상과 스타일은 배제하고 구조와 정보 계층(IA)에만 집중합니다.
* **🔧 핵심 업무 Task:**
    * PRD의 기능 목록을 기반으로 주요 화면 스케치
    * 화면 간의 이동 흐름(User Flow) 시각화
    * 핵심 페이지(탐색, 내 라이브러리)의 레이아웃 배치
* **🤖 활용 AI 도구:**
    * **Figma (FigJam AI), Miro AI:** 텍스트나 간단한 스케치를 기반으로 사용자 플로우 차트, 사이트맵, 기본 와이어프레임을 자동으로 생성해 줍니다.
    * **Uizard, Wireframe.cc:** 손 스케치 또는 텍스트 프롬프트로 즉각적인 디지털 와이어프레임을 생성합니다.

#### 💡 AI 활용 전략

* **'텍스트(PRD)'를 '다이어그램(Flow)'으로:** 1단계의 '사용자 여정 맵' 텍스트를 FigJam AI에 입력하고 "이 텍스트로 사용자 플로우 다이어그램을 만들어줘"라고 요청하여 시각화 작업을 자동화합니다.
* **빠른 구조 검증:** AI로 여러 버전의 와이어프레임을 빠르게 생성하여, 1단계의 '페르소나'가 이 구조에서 'Pain Point'를 해결할 수 있는지 신속하게 검증합니다.

#### ✍️ 예시 프롬프트

> **[사용자 플로우 생성 프롬프트 (FigJam AI)]**
> "Create a user flow diagram based on this user story:
> 'As a user, I want to find a specific prompt, so that I can use it for my task.'
> The flow should start from the 'Explore Page', include 'Search Bar' interaction, 'Filter by Agent' option, 'Search Results Page', and end at the 'Prompt Detail Page'."

> **[와이어프레임 생성 프롬프트 (Uizard/Galileo AI)]**
> "Create a low-fidelity wireframe for a desktop dashboard.
> It must have:
> 1. A thin, icon-only left navigation bar (LNB).
> 2. A global search bar at the top.
> 3. A main content area using a masonry card grid (like Pinterest).
> 4. A 'filter' button next to the search bar.
> Keep it purely structural, no colors or images."

---

### 3. 고품질(Hi-Fi) UI 목업 생성

* **🎯 목표:** 와이어프레임(뼈대)에 무드보드(스타일)를 결합하여, 개발자가 바로 사용할 수 있는 '픽셀-퍼펙트(Pixel-perfect)' 디자인 시안을 만듭니다. (이전 대화에서 우리가 집중했던 작업입니다.)
* **🔧 핵심 업무 Task:**
    * 와이어프레임 위에 확정된 컬러, 타이포그래피, 아이콘 적용
    * 1단계 PRD에 명시된 모든 MVP 화면(탐색, 구독, 마이페이지 등) 디자인
    * 'Pro' 플랜 구독 유도를 위한 시각적 장치(예: 블러 처리, 'Lock' 아이콘) 적용
* **🤖 활용 AI 도구:**
    * **Figma AI (Make Designs):** (요청하신 도구) Figma 내에서 직접 텍스트 프롬프트로 UI를 생성하거나, 기존 와이어프레임을 Hi-Fi로 변환합니다. 반복 수정에 최강입니다.
    * **Galileo AI, Uizard:** 텍스트 프롬프트나 와이어프레임에서 Hi-Fi 디자인을 직접 생성합니다.
    * **(재활용)** **Midjourney, Lovart AI:** 이전에 생성한 상세 UI 프롬프트를 사용하여 고해상도 디자인 시안을 생성합니다. (Figma 작업 전 레퍼런스로 사용)

#### 💡 AI 활용 전략

* **'구조'와 '스타일' 프롬프트 결합:** 2단계의 와이어프레임 프롬프트와 1단계의 무드보드 프롬프트를 결합하여 매우 상세한 Hi-Fi 프롬프트를 만듭니다.
* **'생성' 후 '수정' (Figma AI 활용):** AI가 100% 완벽한 디자인을 만들지 못합니다. Figma AI로 70%를 빠르게 생성한 뒤, 디자이너(인간)가 30%를 다듬거나, "이 버튼을 파란색으로 바꿔줘", "왼쪽 여백을 16px로 변경해줘" 같은 구체적인 수정 프롬프트를 사용합니다.

#### ✍️ 예시 프롬프트

> **[Hi-Fi 목업 생성 프롬프트 (Galileo AI / Figma AI)]**
> (이전 대화에서 상세히 다듬었던 프롬프트입니다)
> "[SCENE: A high-resolution, full-screen UI concept for a 'Prompt Library' desktop web app, main 'Explore' page, dark mode.]
> [LAYOUT: Edge-to-Edge 'Masonry Grid'. A very thin (60px), static, icon-only navigation bar is flush against the far left edge. A minimal top bar contains a global search field.]
> [ELEMENTS: The grid is filled with 'Prompt Cards' of varying heights. Some cards are visually marked with a 'PRO' badge and a small 'Lock' icon. The prompt preview on 'PRO' cards is blurred.]
> [STYLE: Modern, professional, 'Glassmorphism' on the sidebar. Color Palette: Deep charcoal background ($#1E1E24$) with vibrant 'intelligent blue' ($#007AFF$) accents for CTAs and PRO badges.]"

---

### 4. 디자인 시스템 및 컴포넌트화

* **🎯 목표:** Hi-Fi 목업에서 반복적으로 사용되는 UI 요소(버튼, 카드, 인풋창 등)를 '컴포넌트'로 분리하여, 디자인의 일관성을 유지하고 개발 효율성을 높입니다.
* **🔧 핵심 업무 Task:**
    * 공통 컴포넌트(Atom, Molecule) 식별
    * 컴포넌트별 상태(State) 정의 (예: Default, Hover, Pressed, Disabled)
    * 색상, 글꼴, 간격(Spacing) 등을 변수로 정의 (디자인 토큰)
* **🤖 활용 AI 도구:**
    * **Figma AI (Make Designs):** Hi-Fi 목업의 특정 요소를 선택하고 "이것으로 컴포넌트를 만들어줘"라고 지시할 수 있습니다.
    * **Galileo AI:** 디자인 생성 시 자동으로 컴포넌트와 스타일 가이드를 생성해 줍니다.
    * **Anima, Locofy.ai:** Figma 디자인을 분석하여 자동으로 디자인 시스템을 감지하고, 개발자가 사용할 코드로 변환(3단계)할 준비를 합니다.

#### 💡 AI 활용 전략

* **'생성' 후 '추출':** Hi-Fi 목업을 먼저 완성한 뒤, AI를 이용해 목업에서 사용된 스타일(색상, 폰트)을 '추출(Extract)'하여 스타일 가이드를 만듭니다.
* **'변형(Variant)' 자동화:** `Button-Primary` 컴포넌트를 하나 만든 뒤, Figma AI에게 "이 컴포넌트의 Hover, Disabled, Secondary(Outline) 버전을 생성해줘"라고 지시하여 변형(Variant) 생성을 자동화합니다.

#### ✍️ 예시 프롬프트

> **[컴포넌트 생성 프롬프트 (Figma AI)]**
> (Figma에서 파란색 '구독하기' 버튼을 선택한 상태)
> "Turn this element into a new component named 'Button-Primary'.
> Then, create 3 variants:
> 1. 'Hover' state with 90% opacity.
> 2. 'Disabled' state with gray background ($#555555$) and lighter text.
> 3. 'Secondary' variant with a blue outline ($#007AFF$) and transparent background."

> **[스타일 추출 프롬프트 (Figma AI)]**
> (디자인 시안을 열어둔 상태)
> "Analyze this entire page. Extract all used colors and font styles, and generate them as local styles (Design Tokens) in the sidebar."

---
