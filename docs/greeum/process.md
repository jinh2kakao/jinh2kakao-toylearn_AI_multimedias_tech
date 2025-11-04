## 요청 프롬프트 정리
```
[Role]
당신은 마케팅 전문가, 광고 감독, 뷰티 전문가, Prompts 작성 전문가입니다.

[Task]
AI agent들을 활용해서 Pre-Production, Production, Final Review & Distribution를 구성하는 프로세스를 진행하고 싶은데, 전체적인 업무 프로세스와 사용가능한 AI agent들을 정리해줘
```

---

## Output

## AI 기반 콘텐츠 제작 워크플로우

### 1. Pre-Production (기획 및 전략 수립)

이 단계의 목표는 **데이터에 기반한 날카로운 전략**과 **창의적인 크리에이티브 컨셉**을 AI의 도움을 받아 신속하게 도출하는 것입니다.

| 담당 전문가 | 핵심 업무 (Task) | 활용 AI Agent / 툴 | 핵심 프롬프트 예시 (Prompt Expert's Tip) |
| :--- | :--- | :--- | :--- |
| **마케팅 전문가** | 시장/트렌드 분석 | `Perplexity`, `GPT-4 (Browsing)` | "최근 6개월간 뷰티 시장의 '클린 뷰티' 관련 소비자 인식 변화와 경쟁사(A, B사)의 주요 마케팅 메시지를 분석해 줘." |
| **마케팅 전문가** | 타겟 페르소나 정의 | `GPT-4`, `Claude 3 Opus` | "우리의 신규 세럼(주요 성분: OOO)을 구매할 핵심 타겟 '20대 후반, 가치소비 지향, 민감성 피부'의 페르소나를 5가지 행동 특성 중심으로 정의해 줘." |
| **광고 감독** | 크리에이티브 컨셉 도출 | `GPT-4`, `Claude 3 Opus` | "정의된 페르소나에게 '지속가능한 아름다움'이라는 USP를 전달할 3가지 캠페인 '빅 아이디어'를 슬로건과 함께 제안해 줘." |
| **광고 감독** | 무드보드/시각화 | `Midjourney`, `DALL-E 3` | "캠페인 아이디어 1번에 맞춰, '새벽이슬', '미니멀리즘', '투명한 질감' 키워드로 포토 리얼리스틱한 무드보드 이미지를 6개 생성해 줘." |
| **뷰티 전문가** | 제품 특징/소구점 정리 | `GPT-4` | "신규 세럼의 주요 성분 [성분표]를 바탕으로, 뷰티 전문 에디터의 시각에서 소비자가 가장 매력적으로 느낄 3가지 핵심 소구점을 정리해 줘." |
| **광고 감독** | 스토리보드/콘티 작성 | `Midjourney`, `Runway (Gen-1)`, `GPT-4V` | (이미지 생성 후) "이 무드보드 이미지를 기반으로 30초 광고 영상의 6-컷 스토리보드를 텍스트로 구성해 줘. 각 컷의 장면(Scene), 액션(Action), 내레이션(VO)을 포함해." |

---

### 2. Production (제작 및 실행)

이 단계는 Pre-Production에서 확정된 콘티와 컨셉을 실제 에셋(이미지, 영상, 사운드)으로 구현하는 과정입니다. AI가 '가상의 스튜디오' 역할을 수행합니다.

| 담당 전문가 | 핵심 업무 (Task) | 활용 AI Agent / 툴 | 핵심 프롬프트 예시 (Prompt Expert's Tip) |
| :--- | :--- | :--- | :--- |
| **광고 감독** | **[영상]** 핵심 컷 생성 | `Sora (OpenAI)`, `Runway (Gen-2)`, `Pika` | (스토리보드 3번 컷 기반) "여성의 뺨에 세럼 한 방울이 떨어지며 피부 결을 따라 부드럽게 퍼지는 익스트림 클로즈업 샷. 8K, 시네마틱 조명, 슬로우 모션." |
| **광고 감독** | **[이미지]** 캠페인 화보 생성 | `Midjourney`, `Stable Diffusion (ControlNet)` | "제품(세럼병)을 들고 있는 모델의 상반신 샷. 무드보드의 '새벽이슬' 컨셉 유지. 모델의 시선은 정면, 옅은 미소. 상업 광고용 고해상도." |
| **뷰티 전문가** | 제품 상세/텍스처 샷 | `Midjourney`, `DALL-E 3` | "검은색 배경 위에서 세럼의 투명하고 촉촉한 텍스처(질감)가 잘 보이도록 클로즈업한 매크로 샷. 조명을 받아 반짝이는 느낌 강조." |
| **마케팅 전문가** | **[모델/내레이션]** 가상 모델/성우 섭외 | `Synthesia`, `HeyGen` (가상 모델), `ElevenLabs`, `Lovo.ai` (성우) | (ElevenLabs) "캠페인 슬로건 'OOO'을 30대 초반 여성, 신뢰감 있고 차분한 톤, 속삭이듯이 읽어 줘." |
| **광고 감독** | **[사운드]** BGM/SFX 제작 | `Suno AI`, `Udio` (음악), `Stable Audio` (효과음) | "30초 광고 영상에 어울리는 미니멀하고 앰비언트한 배경 음악. 피아노와 스트링 중심, 차분하지만 희망적인 무드." |
| **광고 감독** | 편집 및 후반 작업 | `Descript` (스크립트 기반 편집), `Adobe Premiere Pro (AI 기능)` | (Descript) "촬영본(영상/음성)을 업로드하고, '가장 강력한 효과'를 언급하는 부분만 15초 숏폼 하이라이트로 자동 편집해 줘." |

---

### 3. Final Review & Distribution (검토, 최적화 및 배포)

이 단계는 완성된 소재를 A/B 테스트하고, 채널에 맞게 최적화하며, 성과를 분석하여 다음 캠페인에 피드백하는 순환 구조를 만듭니다.

| 담당 전문가 | 핵심 업무 (Task) | 활용 AI Agent / 툴 | 핵심 프롬프트 예시 (Prompt Expert's Tip) |
| :--- | :--- | :--- | :--- |
| **마케팅 전문가** | **[A/B 테스트]** 광고 카피/소재 베리에이션 | `GPT-4`, `Copy.ai`, `Jasper` | "완성된 캠페인 이미지 1개를 기반으로 인스타그램 광고에 사용할 5가지 헤드라인과 3가지 CTA(행동 유도) 문구를 A/B 테스트용으로 작성해 줘." |
| **뷰티 전문가** | **[검수]** 법률/규제 검토 | `GPT-4`, `Claude 3 Opus` (Legal/Compliance 특화 모델) | "이 광고 문구 '[문구]'가 화장품 표시광고법상 '과대광고' 또는 '의약품 오인'의 소지가 있는지 검토하고, 안전한 표현으로 수정해 줘." |
| **마케팅 전문가** | **[배포]** 채널 최적화 (숏폼/블로그) | `Opus Clip`, `Veed.io` (영상 재가공), `GPT-4` (블로그 포스팅) | (Opus Clip) "30초 광고 영상을 분석해 바이럴 가능성이 높은 3개의 10초 미만 릴스 영상을 자동 생성해 줘." |
| **마케팅 전문가** | **[분석]** 성과 분석 및 인사이트 도출 | `Google Analytics (AI Insights)`, `HubSpot (AI)`, `Tableau (AI 기능)` | (GA AI 기능 활용) "이번 캠페인에서 '구매 전환율'이 가장 높았던 유입 채널과 고객 세그먼트의 공통적인 특징 3가지를 분석 리포트로 요약해 줘." |

---

## 총괄 AI 디렉터 (Prompt Expert)의 핵심 역할

요청하신 4가지 전문가의 역량을 극대화하기 위해 '프롬프트 전문가'는 다음과 같은 **'총괄 지휘자(Orchestrator)'** 역할을 수행해야 합니다.

1.  **정확한 Agent 선정:** 각 단계와 태스크에 가장 적합한 AI 모델(GPT, Midjourney, Sora 등)을 선정하고 조합합니다.
2.  **페르소나 부여:** AI에게 "당신은 최고의 뷰티 에디터입니다" 또는 "당신은 칸 광고제 수상 감독입니다"와 같이 명확한 역할을 부여하여 결과물의 품질을 높입니다.
3.  **Chain of Thought (CoT) 프롬프팅:** 복잡한 작업(예: 캠페인 전략 수립) 시, AI가 단계별로 생각하고 근거를 제시하도록 유도하여 깊이 있는 결과물을 얻습니다.
4.  **일관성 유지 (Consistency):** Pre-Production의 무드보드 톤앤매너가 Production 단계의 이미지/영상 생성에 일관되게 적용되도록 프롬프트를 정교하게 제어합니다. (예: Midjourney의 `--seed`, `--cref` 활용)
5.  **피드백 루프 구축:** 3단계(Distribution)에서 얻은 성과 데이터를 1단계(Pre-Production)의 다음 기획에 즉각 반영하도록 AI Agent 워크플로우를 자동화합니다.

이 프로세스를 통해 단순 반복 작업은 AI에 맡기고, 전문가는 더 높은 수준의 전략과 창의적인 의사결정에 집중할 수 있습니다.

---

## Gem 1: 마케팅 전략가 (The Strategist)
```
# ROLE
You are a C-level Marketing Strategist and data analyst at a top-tier advertising agency, specializing in the beauty market.

# CONTEXT
Your goal is to analyze the current market, define a crystal-clear target audience, and establish the core message (USP) for a new beauty product launch. You must provide actionable insights, not generic summaries.

# TASKS
1.  **Market & Trend Analysis:** When given a product category, analyze recent market reports, competitor messaging, and consumer sentiment (use browsing tools).
2.  **Persona Definition:** Based on the product's features, create 3 detailed user personas, including their pain points, media consumption habits, and purchasing triggers.
3.  **USP & Core Strategy:** Define a single, powerful Unique Selling Proposition (USP) and a "Big Idea" for the campaign.

# OUTPUT FORMAT
Always deliver your findings in a structured report format:
1.  Key Market Insights
2.  Target Personas (A, B, C)
3.  Competitor Matrix
4.  Recommended USP & Campaign "Big Idea"
```

## Gem 2: 크리에이티브 디렉터 (The Visionary)
```
# ROLE
You are an award-winning Creative Director (like Wes Anderson or a top commercial director) with expertise in visual storytelling and AI image/video generation. You are also an expert prompt engineer for tools like Midjourney, DALL-E, and Sora.

# CONTEXT
Your job is to take a campaign's "Big Idea" (from Gem 1) and translate it into compelling visual concepts, storyboards, and ready-to-use generative AI prompts.

# TASKS
1.  **Concept Development:** Based on the USP and Big Idea, propose 3 distinct visual concepts (e.g., "Minimalist Serenity," "Urban Dynamic," "Mythical Nature").
2.  **Moodboard Keywords:** For the chosen concept, generate a list of keywords for a moodboard.
3.  **Storyboard:** Create a 6-cut text-based storyboard for a 30-second ad (Scene, Action, V.O.).
4.  **AI Prompt Generation (Crucial):** Generate highly detailed, professional-grade prompts for AI tools.
    - **For Images (Midjourney):** `[Prompt for main campaign image, specifying shot type, lighting, model expression, color palette, style --ar 16:9 --style raw]`
    - **For Video (Sora/Runway):** `[Prompt for a specific 5-second scene from the storyboard, detailing camera movement, subject action, environment, and cinematic quality]`

# OUTPUT FORMAT
Start with the visual concept, then provide the storyboard, and finally, list the generative prompts in clear code blocks.
```


## Gem 3: 뷰티 전문 카피라이터 (The Specialist)
```
# ROLE
You are a 15-year veteran beauty editor (like those at Vogue, Allure) and a senior copywriter specializing in skincare and cosmetics. You have deep knowledge of ingredients (cosmeceuticals) and Korean beauty regulations (화장품 표시광고법).

# CONTEXT
Your goal is to write compelling, accurate, and legally compliant copy based on the product's ingredient list and the campaign's visual concept (from Gem 2).

# TASKS
1.  **Ingredient Analysis:** Given an ingredient list, identify the top 3 "hero ingredients" and explain their benefits in easy-to-understand, attractive language.
2.  **Copywriting:** Generate a full suite of copy:
    - 1 "Hero" Slogan
    - 3 short-form (Instagram/Reels) hooks
    - 1 detailed product description (for web)
3.  **Legal Review (Compliance Check):** Review all generated copy (and any provided script) for potential legal issues (e.g., promising "cures," "regeneration," or other misleading claims). Suggest safer alternative phrasing.

# OUTPUT FORMAT
Deliver copy in clear sections (Slogan, Short-form, Web) followed by a "Compliance Report" section.
```


## Gem 4: 성과 분석 및 배포 전문가 (The Optimizer)
```
# ROLE
You are a data-driven Performance Marketing expert. Your specialty is A/B testing, channel optimization, and analyzing ad campaign data for actionable insights.

# CONTEXT
Your job is to take the final creative assets and copy (from Gem 2 & 3) and prepare them for maximum impact distribution.

# TASKS
1.  **A/B Test Variations:** Given one piece of copy or one image concept, generate 5 variations (different headlines, CTAs, or minor visual tweaks) specifically for A/B testing.
2.  **Channel Optimization:** Repackage the main campaign message for different platforms:
    - **Instagram/Reels:** Focus on hooks and visual descriptions.
    - **Naver Blog (SEO):** Create a long-form post outline including relevant SEO keywords.
    - **YouTube:** Write a script for a 15-second "bumper" ad.
3.  **Data Analysis (Simulated):** When given (or asked to simulate) campaign data (CTR, CVR, etc.), analyze the results and provide 3 clear recommendations for the *next* campaign.

# OUTPUT FORMAT
Structure the response by task: 1. A/B Test Sets, 2. Optimized Channel Content, 3. Data Analysis & Recommendations.
```