
🎨 Figma AI 기반 Phase 2: UI/UX 디자인 상세 가이드
이 단계는 Figma 생태계 내에서 4가지 핵심 Task를 수행합니다.

(FigJam) 무드보드 및 비주얼 컨셉 확립

(FigJam & Figma) 와이어프레임(Lo-Fi) 및 사용자 플로우(Flow) 설계

(Figma AI) 고품질(Hi-Fi) UI 목업 생성

(Figma AI) 디자인 시스템 및 컴포넌트화

1. 무드보드 및 비주얼 컨셉 확립 (in FigJam)
🎯 목표: 서비스의 전반적인 '느낌과 분위기(Look and Feel)'를 FigJam 보드에서 정의합니다. PRD의 키워드(예: "전문적", "AI", "라이브러리")를 시각 언어로 번역하고 팀과 공유합니다.

🔧 핵심 업무 Task:

핵심 키워드 기반 시각적 방향성 탐색

메인 컬러 팔레트 (Primary, Secondary, Accent) 정의

타이포그래피(글꼴) 시스템 정의

아이콘 및 이미지 스타일 컨셉 수집

🤖 활용 AI 도구:

FigJam AI: 키워드(예: "AI 프롬프트 라이브러리")만으로 즉시 무드보드 템플릿과 관련 레퍼런스 이미지를 생성합니다.

Figma Plugins (예: Magician, Musho, Builder.io AI): FigJam/Figma 내에서 텍스트 프롬프트로 로고 컨셉, 아이콘, 영감을 주는 UI 조각을 직접 생성하여 보드에 추가합니다.

💡 AI 활용 전략
'키워드'에서 '시각적 영감'으로 (FigJam AI): FigJam AI에 1단계 PRD의 핵심 키워드를 입력하여 관련 이미지, 색상 팔레트, UI 스니펫을 빠르게 수집하고 분류합니다.

Figma를 허브로 활용: 외부 AI(Midjourney 등)에서 생성한 이미지를 별도로 관리하는 대신, Figma 플러그인을 사용하거나 생성된 이미지를 FigJam 보드로 즉시 가져와 팀의 피드백 루프를 단축시킵니다.

✍️ 예시 프롬프트
[무드보드 생성 프롬프트 (FigJam AI)] "Generate a moodboard for a 'Prompt Library' subscription service. Include sections for:

Color Palette (dark mode, tech-focused, intelligent blue)

Typography (clean, modern sans-serif)

UI Inspiration (data-rich dashboards, glassmorphism)

Icon Style (minimalist, line art)"

[아이콘 컨셉 생성 프롬프트 (Figma Plugin Magician)] (Figma에서 사각형 선택 후) "A minimalist, vector icon combining a 'brain' and a 'book', line art style, white."

2. 와이어프레임(Lo-Fi) 및 사용자 플로우(Flow) 설계 (in FigJam & Figma)
🎯 목표: 1단계의 '사용자 스토리(User Stories)'를 FigJam에서 '사용자 플로우(Flow)'로 시각화하고, 이를 Figma에서 '뼈대(Wireframe)'로 변환합니다.

🔧 핵심 업무 Task:

PRD의 기능 목록을 기반으로 화면 간의 이동 흐름(User Flow) 시각화

FigJam의 플로우를 기반으로 Figma에서 주요 화면 스케치(Lo-Fi)

정보 구조(IA) 및 핵심 페이지 레이아웃 배치

🤖 활용 AI 도구:

FigJam AI: 텍스트, 스티커, 심지어 PRD의 사용자 스토리를 붙여넣기만 하면 자동으로 연결된 플로우 차트와 다이어그램을 생성합니다.

Figma AI (Make) 및 플러그인 (예: Wireframe Designer, Autoflow):

Autoflow: FigJam이나 Figma 내의 프레임 간에 자동으로 플로우 화살표를 연결합니다.

Wireframe Designer: 텍스트 프롬프트로 즉각적인 디지털 와이어프레임 컴포넌트(예: "로그인 폼")를 생성합니다.

💡 AI 활용 전략
'텍스트(PRD)'를 '다이어그램(Flow)'으로: 1단계의 '사용자 여정 맵' 텍스트를 FigJam AI에 입력하고 "이 텍스트로 사용자 플로우 다이어그램을 만들어줘"라고 요청하여 시각화 작업을 자동화합니다.

'플로우'에서 '와이어프레임'으로: FigJam에서 확정된 플로우 차트의 각 단계를 Figma 프레임으로 가져온 뒤, Figma AI 기능이나 플러그인을 사용하여 "탐색 페이지 와이어프레임 생성" 같은 명령으로 기본 구조를 빠르게 만듭니다.

✍️ 예시 프롬프트
[사용자 플로우 생성 프롬프트 (FigJam AI)] "Create a user flow diagram based on this user story: 'As a user, I want to find a specific prompt, so that I can use it for my task.' The flow should start from the 'Explore Page', include 'Search Bar' interaction, 'Filter by Agent' option, 'Search Results Page', and end at the 'Prompt Detail Page'."

[와이어프레임 생성 프롬프트 (Figma AI / Plugin)] "Create a low-fidelity wireframe for a desktop dashboard. It must have:

A thin, icon-only left navigation bar (LNB).

A global search bar at the top.

A main content area using a masonry card grid (like Pinterest).

A 'filter' button next to the search bar. Keep it purely structural, no colors or images."

3. 고품질(Hi-Fi) UI 목업 생성 (in Figma AI)
🎯 목표: 와이어프레임(뼈대)에 1단계의 무드보드(스타일)를 결합하여, 개발자가 바로 사용할 수 있는 '픽셀-퍼펙트(Pixel-perfect)' 디자인 시안을 Figma 내에서 완성합니다.

🔧 핵심 업무 Task:

와이어프레임 위에 확정된 컬러, 타이포그래피, 아이콘 적용

1단계 PRD에 명시된 모든 MVP 화면(탐색, 구독, 마이페이지 등) 디자인

'Pro' 플랜 구독 유도를 위한 시각적 장치(예: 블러 처리, 'Lock' 아이콘) 적용

🤖 활용 AI 도구:

Figma AI (Make): (요청하신 핵심 기능) 텍스트 프롬프트로 UI를 직접 생성하거나, 기존 와이어프레임을 선택하고 "이것을 다크 모드 Glassmorphism 스타일로 바꿔줘"라고 지시하여 Hi-Fi로 즉시 변환합니다. 반복 수정에 가장 강력합니다.

Figma Plugins (예: Magician, Musho): AI를 사용하여 이미지, 아이콘, 심지어 UI에 맞는 텍스트(UX Writing)까지 생성하여 Hi-Fi 디자인을 채웁니다.

💡 AI 활용 전략
'생성' 후 '수정' (Iterative Design): Figma AI로 70%의 Hi-Fi 디자인을 빠르게 생성합니다. 그 후, 디자이너(인간)가 30%를 다듬거나, "이 버튼을 파란색으로 바꿔줘", "왼쪽 여백을 16px로 변경해줘" 같은 구체적인 수정 프롬프트를 사용하여 디자인을 완성합니다.

'구조'와 '스타일' 프롬프트 결합: 2단계의 와이어프레임 구조 프롬프트와 1단계의 무드보드 스타일 프롬프트를 결합하여 매우 상세한 Hi-Fi 프롬프트를 만듭니다.

✍️ 예시 프롬프트
[Hi-Fi 목업 생성 프롬프트 (Figma AI 'Make')] (Figma에서 빈 프레임을 선택한 상태) "[SCENE: A high-resolution, full-screen UI concept for a 'Prompt Library' desktop web app, main 'Explore' page, dark mode.] [LAYOUT: Edge-to-Edge 'Masonry Grid'. A very thin (60px), static, icon-only navigation bar is flush against the far left edge. A minimal top bar contains a global search field.] [ELEMENTS: The grid is filled with 'Prompt Cards' of varying heights. Some cards are visually marked with a 'PRO' badge and a small 'Lock' icon. The prompt preview on 'PRO' cards is blurred.] [STYLE: Modern, professional, 'Glassmorphism' on the sidebar. Color Palette: Deep charcoal background ($#1E1E24$) with vibrant 'intelligent blue' ($#007AFF$) accents for CTAs and PRO badges.]"

4. 디자인 시스템 및 컴포넌트화 (in Figma AI)
🎯 목표: Hi-Fi 목업에서 반복적으로 사용되는 UI 요소(버튼, 카드 등)를 '컴포넌트'로 분리하고 '변수(Variables)'로 관리하여, 디자인의 일관성을 유지하고 개발 효율성을 극대화합니다.

🔧 핵심 업무 Task:

공통 컴포넌트(Atom, Molecule) 식별

컴포넌트별 상태(State) 정의 (예: Default, Hover, Pressed, Disabled)

색상, 글꼴, 간격(Spacing) 등을 변수(Variables)로 정의 (디자인 토큰)

🤖 활용 AI 도구:

Figma AI (Make): Hi-Fi 목업의 특정 요소(예: 버튼)를 선택하고 "이것으로 컴포넌트를 만들어줘"라고 지시할 수 있습니다.

Figma AI (Make) + Variables: 컴포넌트를 만든 후, "이 컴포넌트의 Hover, Disabled, Secondary(Outline) 버전을 생성해줘"라고 지시하여 'Variants(변형)' 생성을 자동화합니다.

Figma AI (Make) + Styles: "이 페이지의 모든 색상과 폰트 스타일을 추출해서 로컬 스타일(Local Styles)로 만들어줘"라고 지시하여 디자인 토큰 생성을 자동화합니다.

💡 AI 활용 전략
'변형(Variant)' 자동화: Button-Primary 컴포넌트를 하나 만든 뒤, Figma AI에게 변형(Variant) 생성을 지시하여 반복 작업을 최소화합니다.

'스타일'에서 '토큰'으로: Hi-Fi 목업을 먼저 완성한 뒤, AI를 이용해 목업에서 사용된 스타일(색상, 폰트)을 '추출(Extract)'하여 변수(Variables) 및 스타일 가이드(Local Styles)를 만듭니다.

✍️ 예시 프롬프트
[컴포넌트 생성 및 변형 프롬프트 (Figma AI 'Make')] (Figma에서 파란색 '구독하기' 버튼을 선택한 상태) "Turn this element into a new component named 'Button-Primary'. Then, create 3 variants:

'Hover' state with 90% opacity.

'Disabled' state with gray background ($#555555$) and lighter text.

'Secondary' variant with a blue outline ($#007AFF$) and transparent background."

[스타일 추출 프롬프트 (Figma AI 'Make')] (디자인 시안을 열어둔 상태) "Analyze this entire page. Extract all used colors and font styles, and generate them as local styles (Design Tokens) in the sidebar."