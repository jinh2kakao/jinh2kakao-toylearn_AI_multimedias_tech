# 📄 제품 요구사항 명세서 (PRD): AI 프롬프트 라이브러리 v1.0

* **문서 버전:** 1.0
* **작성일:** 2025년 11월 6일
* **작성자:** UI/UX 전문가 (Gemini)
* **최종 업데이트:** [모든 수정사항 반영 완료]

---

## 1. 제품 개요 (Overview)

* **제품명:** AI 프롬프트 라이브러리 및 관리 플랫폼 (가칭)
* **목표:** 사용자가 다양한 AI 서비스(텍스트, 이미지 등)에서 사용할 수 있는 고품질의 프롬프트를 **발견, 생성, 관리, 공유**할 수 있는 중앙화된 허브를 제공합니다.
* **핵심 가치:**
    * **생산성 향상:** 검증된 프롬프트를 즉시 찾아 사용함으로써 작업 시간을 단축시킵니다.
    * **품질 표준화:** R.T.I. (역할, 과업, 지침) 프레임워크를 통해 구조화된 프롬프트 작성을 유도합니다.
    * **워크플로우 혁신:** 단일 AI가 아닌, 여러 AI를 단계별로 활용하는 '시퀀셜 프롬프트'를 제공하여 복잡한 작업을 지원합니다.
    * **개인화:** '내 라이브러리' 및 '개인 AI 키(BYOK)'를 통해 사용자 맞춤형 환경을 제공합니다.

## 2. 대상 사용자 (User Personas)

1.  **프롬프트 소비자 (Prompt Consumer):**
    * **설명:** 마케터, 작가, 학생 등 AI를 도구로 활용하는 일반 사용자.
    * **핵심 니즈:** 원하는 결과를 빠르게 얻을 수 있는 검증된 프롬프트를 즉시 찾고 사용하기를 원함.
2.  **프롬프트 생성자 (Prompt Creator/Engineer):**
    * **설명:** 개발자, 디자이너, 파워 유저 등 자신만의 고도화된 프롬프트를 설계하는 사용자.
    * **핵심 니즈:** 프롬프트를 구조적(R.T.I.)으로 작성하고, 비공개로 저장(MyLibrary)하며, 성과를 테스트하기를 원함.
3.  **프로 사용자 (PRO User):**
    * **설명:** 전문가, 팀 단위 사용자.
    * **핵심 니즈:** 모든 PRO 프롬프트 접근, AI 어시스턴트, API 키 연동 등 고급 기능을 통한 최대의 생산성을 원함.

## 3. 전역 요구사항 (Global Requirements)

모든 페이지에 공통으로 적용되는 시스템 수준의 요구사항입니다.

* **G-1: 전역 네비게이션 시스템 (Persistent Navigation)**
    * **LNB (Left Navigation Bar):**
        * `w-[60px]`, 아이콘 전용, Glassmorphism 스타일 (`bg-white/5`, `backdrop-blur-xl`).
        * 모든 페이지(상세 페이지 포함)에서 항상 표시되며, 클릭 시 해당 메인 페이지로 즉시 이동해야 합니다. (데스크톱/태블릿 기준)
    * **Top Bar (Header):**
        * `h-16 (64px)`, `backdrop-blur-sm bg-[#1E1E24]/80` 스타일.
        * 모든 페이지에서 항상 표시되며, '전역 검색창'을 포함합니다.
* **G-2: 반응형 UI (Responsive Design)**
    * **모바일 (`< 768px`):**
        * LNB는 숨겨지며, Top Bar 좌측에 '햄버거 메뉴' 아이콘이 표시되어야 합니다. (클릭 시 LNB가 오버레이로 열림)
        * 모든 다중 컬럼 레이아웃(그리드, 2단 레이아웃)은 1단 컬럼(수직 스택)으로 변경되어야 합니다.
    * **태블릿 (`768px ~ 1024px`):**
        * LNB는 `w-[60px]`로 표시됩니다.
        * 메인 콘텐츠 그리드는 2-Column으로 표시됩니다.
    * **데스크톱 (`> 1024px`):**
        * 모든 레이아웃이 최대(3-Column 또는 2-Column)로 표시됩니다.
* **G-3: "내 프롬프트" 식별 (My Prompt Badge)**
    * `Explore`, `Trending Now` 등 모든 공개 페이지의 프롬프트 카드 중, 현재 **로그인한 사용자가 생성한 프롬프트**에는 명확한 식별 배지(예: "My Prompt" 뱃지, 스타일: `bg-[#007AFF]/20 text-[#007AFF]`)가 표시되어야 합니다.

---

## 4. 기능 명세서 (Feature Breakdown)

### Epic 1: 프롬프트 탐색 (Prompt Discovery)

#### Feature 1.1: Explore Prompts (탐색)

* **User Story:** 사용자는 커뮤니티의 모든 프롬프트를 시각적으로 탐색하여 새로운 아이디어를 얻고 싶다.
* **Reqs:**
    * `Masonry` (가변 높이) 그리드 레이아웃 (반응형: 3/2/1 컬럼).
    * 헤더에 "Create New Prompt" CTA 버튼이 포함되어야 합니다. (`MyLibrary`와 동일)
    * 모든 카드는 해당 '상세 페이지'로 링크되어야 합니다.
    * `G-3` 요구사항(내 프롬프트 배지)을 준수해야 합니다.

#### Feature 1.2: Trending Now (트렌딩)

* **User Story:** 사용자는 현재 가장 인기 있는 프롬프트를 확인하여 최신 트렌드를 활용하고 싶다.
* **Reqs:**
    * `Masonry` 그리드 레이아웃.
    * 필터 탭 ("Today", "This Week", "This Month")이 제공되어야 합니다.
    * 모든 카드는 해당 '상세 페이지'로 링크되어야 합니다.

#### Feature 1.3: 고급 검색 (Instant Search)

* **User Story:** 사용자는 키워드와 상세 필터를 조합하여 원하는 프롬프트를 즉시 찾고 싶다.
* **Reqs:**
    * Top Bar의 검색창에 포커스(focus) 시, 메인 콘텐츠 영역이 '즉각적인 검색 모드' UI로 전환되어야 합니다.
    * **UI:** 2단 레이아웃 (좌: 결과, 우: 필터).
    * **좌측 (결과):**
        * *초기 상태 (타이핑 전):* "최근 검색어" 목록 표시.
        * *활성 상태 (타이핑 중):* 실시간 '텍스트 자동완성' 및 '일치하는 프롬프트' 목록(간소화된 카드) 표시.
    * **우측 (필터):**
        * `bg-[#2A2A32]` 배경의 고정 필터 패널.
        * 필터 항목: **호환 AI** (멀티셀렉트), **비즈니스 카테고리** (멀티셀렉트), **프롬프트 유형** (토글).

#### Feature 1.4: PRO 구독 유도 (Upsell Modal)

* **User Story:** 서비스는 무료 사용자가 잠긴 'PRO' 프롬프트를 클릭했을 때, 즉시 구독을 유도하여 수익을 창출하고 싶다.
* **Reqs:**
    * `PRO` 배지가 붙은 프롬프트 카드 클릭 시, '구독 유도 모달'이 즉시 표시되어야 합니다.
    * 배경은 `backdrop-blur-sm` 처리되어야 합니다.
    * 모달에는 PRO 기능 목록과 명확한 "Upgrade to PRO" CTA가 포함되어야 합니다.

### Epic 2: 프롬프트 관리 (Prompt Management)

#### Feature 2.1: My Prompt Library (내 라이브러리)

* **User Story:** 사용자는 자신이 직접 생성한 프롬프트만을 모아보고 관리(수정/삭제)하고 싶다.
* **Reqs:**
    * `Standard` (고정 높이) 그리드 레이아웃 (반응형: 3/2/1 컬럼).
    * 헤더에 "Create New Prompt" CTA 버튼 포함.
    * 프롬프트가 없을 경우, "Empty State" (빈 상태 UI)가 "Create New Prompt" CTA와 함께 표시되어야 합니다.
    * 각 카드에는 'Edit' 및 'Delete' 아이콘 버튼이 노출되어야 합니다.

#### Feature 2.2: Saved Prompts (즐겨찾기)

* **User Story:** 사용자는 Explore 등에서 '저장'한 커뮤니티 프롬프트만 모아보고 싶다.
* **Reqs:**
    * `Standard` 그리드 레이아웃.
    * 프롬프트가 없을 경우 "Empty State" 표시.

#### Feature 2.3: 프롬프트 생성/편집 페이지 (Create/Edit Page)

* **User Story:** 사용자는 구조화된 R.T.I. 폼을 통해 고품질의 프롬프트를 쉽게 작성하고 수정하고 싶다.
* **Reqs (Layout):** 중앙 정렬된 1단 컬럼 (`max-w-4xl`).
* **Reqs (Form):**
    * **R.T.I. 구조:** 'Title', 'Context'(유형/도메인), 'Role', 'Task', 'Instructions' 섹션별 입력 필드 제공.
    * **AI 서비스 선택기:** '호환 AI'를 위한 멀티셀렉트 컴포넌트. (입력창에 'Pill' 태그 표시, 클릭 시 카테고리(Text/Image/Code)별 검색/선택이 가능한 팝오버 표시)
* **Reqs (AI Assistant):**
    * 'Instructions' 섹션 내 "Ask AI Assistant" (인라인 도움) 버튼.
    * 최종 저장 버튼 좌측에 "Review with AI" (AI 검토) 버튼. (F-3.1의 BYOK 기능에 의존)

#### Feature 2.4: 표준 프롬프트 상세 (Standard Detail Page)

* **User Story:** 사용자는 프롬프트의 상세 내용을 명확히 확인하고, 소유권에 따라 적절한 행동(저장/수정)을 하고 싶다.
* **Reqs (Layout):**
    * **모든** 프롬프트 상세 페이지의 표준 레이아웃으로 사용.
    * 2단 컬럼 (좌: 콘텐츠, 우: 액션). (모바일에서는 수직 스택)
* **Reqs (Content - Left):**
    * **Breadcrumbs:** 상위 페이지로 이동 경로 표시 (예: "Explore / Prompt Title").
    * **R.T.I. 섹션:** "Role", "Task", "Instructions"가 명확히 구분되어 표시.
* **Reqs (Actions - Right):**
    * **Context Card:** '유형', '도메인' 등 메타데이터 표시.
    * **Dynamic Action Card (핵심):** 프롬프트 소유권에 따라 버튼이 동적으로 변경되어야 함.
        * *소유자 (Owner):* "Run", "Edit", "Copy", "Delete"
        * *타인 (Visitor):* "Run", "Save to Library", "Copy"

#### Feature 2.5: 시퀀셜 프롬프트 상세 (Sequential Detail Page)

* **User Story:** 사용자는 여러 AI를 단계별로 사용하는 복잡한 '워크플로우' 프롬프트를 확인하고 사용하고 싶다.
* **Reqs (Layout):** 신규 2단 컬럼 레이아웃 (좌: 워크플로우, 우: 전역 액션).
* **Reqs (Content - Left):**
    * **Vertical Stepper:** "Step 1", "Step 2" ... "Step N"을 시각적으로 연결한 수직 스텝 UI.
    * *각 스텝:* 'Step #', '제목', '사용 AI', '해당 스텝의 프롬프트', '해당 스텝 복사 버튼' 포함.
* **Reqs (Actions - Right):**
    * **Context Card:** '유형: Sequential Workflow' 표시.
    * **Global Action Card:** "Save Workflow", "Copy All Steps" 버튼 제공.

### Epic 3: 사용자 설정 (User & System)

#### Feature 3.1: 설정 > API 키 (Settings > API Keys)

* **User Story:** 사용자는 F-2.3의 'AI 어시스턴트' 기능을 사용하기 위해, 자신의 개인 AI API 키를 안전하게 등록, 수정, 삭제하고 싶다 (BYOK - Bring Your Own Key).
* **Reqs (Layout):** 2단 컬럼 (좌: 설정 서브메뉴, 우: 콘텐츠), 모바일에서 수직 스택.
* **Reqs (Sub-nav):** 'API Keys' 항목이 활성화 상태.
* **Reqs (Content - Right):**
    * BYOK 기능 설명이 담긴 'Info Box'
    * "Add API Key" CTA 버튼.
    * **등록된 키 목록:** '닉네임', 'AI 서비스 타입', '마스킹된 키(...xxxx)', **"Edit" 버튼**, **"Delete" 버튼** 포함.
* **Reqs (Modals):**
    * "Add API Key" 모달: '닉네임', 'AI 서비스 (Select)', 'API Key (Password)' 입력 폼.
    * "Edit API Key" 모달: 기존 정보가 채워진 폼. (키 필드는 "Leave blank to keep..." 플레이스홀더)

#### Feature 3.2: 설정 > 외형 (Settings > Appearance)

* **User Story:** 사용자는 앱의 테마(라이트/다크 모드)를 변경하고 싶다.
* **Reqs:** 'Appearance' 서브메뉴 및 테마 토글 스위치 제공.

#### Feature 3.3: 계정 관리 (Account Page)

* **User Story:** 사용자는 자신의 프로필 정보(이름, 이메일)와 현재 구독 플랜을 확인/관리하고 싶다.
* **Reqs (Layout):** 중앙 정렬된 1단 컬럼 (`max-w-800px`).
* **Reqs (Content):** 'Profile' 카드(정보 수정), 'Subscription' 카드(플랜 관리 CTA) 구분.