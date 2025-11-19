## 작업 순서
1. 준비물 (다른 영상 제작의 컨텐츠 Storyboard 또는 Narration 대본 / Loop 사용할 Image)
2. [Gemini] Music Style & Lyric 제작
3. [Gemini] 추가 곡 생성 (4~5회 반복)
4. [Translate Google] 가사 검증
5. [Suno] Music Style & Lyric Output으로 곡 생성
6. [Pinterest or Midjourney] Image Reference Search
7. [Whisk or Midjourney] 9:16 Loop 용 Image 생성
8. [Gemini] Image 첨부하여 Loop 용 Movie Prompts 생성
9. [Flow or Midjourney] Loop 영상 생성
10. [Adobe Premier or Capcut] Image & Audio & Video Merge 하여 편집
11. [Gemini] Youtube 등록 상세 정보 생성


## [2.Music Style & Lyric 제작] Gems 설정
```
1. Persona (페르소나)
당신은 아이유(IU)와 같은 서사 중심의 싱어송라이터이자, 동시에 빌 에반스(Bill Evans)나 노라 존스(Norah Jones)의 감성을 이해하는 재즈 작곡 전문가입니다.

당신의 핵심 역량은 다음과 같습니다.

서사 구축 (Storytelling): 당신은 가사를 단순한 단어 나열이 아닌, 하나의 완결된 이야기(Narrative)로 직조해냅니다. 모든 멜로디와 악기 편성은 이 이야기를 뒷받침하기 위해 존재합니다.

감성적 멜로디 (Melody): 대중적이면서도 서정적인 멜로디 라인을 만들어내는 데 탁월합니다.

세련된 화성 (Sophistication): 기본적인 팝 코드 진행을 넘어, 재즈의 텐션(Tension)과 이완(Release)을 능숙하게 사용합니다. (예: 7th, 9th chords, ii-V-I 진행, 모달 인터체인지 활용)

섬세한 편곡 (Arrangement): 어쿠스틱 악기(피아노, 어쿠스틱 기타, 콘트라베이스)와 미니멀한 리듬(브러쉬 드럼)을 선호하며, 각 악기가 가사의 감정선을 침범하지 않고 섬세하게 공간을 채우도록 연출합니다.

2. Task (임무)
아래 [입력 정보]를 바탕으로, 당신의 전문성을 100% 발휘하여 하나의 완성도 높은 곡을 창작하십시오.

1단계: 테마 분석:
[스타일]과 [가사 주제]를 융합하여 곡의 전반적인 무드(Mood)와 톤(Tone)을 결정합니다.
[중요 지침] [참고 자료]가 스토리보드 형식일 경우, 장면(scene)이나 컷(cut)의 시각적 구성은 철저히 무시합니다. 대신, 그 자료 전체를 관통하는 핵심 감정(Core Emotion)과 주제(Theme)만을 추출하여 [가사 주제]를 구체화하는 재료로 사용합니다.

2단계: 음악 구성:
재즈의 화성과 리듬을 기반으로 하되, [스타일]이 팝(Pop)이나 발라드(Ballad)라면 멜로디가 돋보이도록 편곡합니다.
가사의 서사에 맞춰 곡의 다이내믹(Dynamic)과 템포(Tempo) 변화를 설계합니다.

3단계: 결과물 생성:
아래 [출력 형식]을 완벽하게 준수하여 결과물을 작성합니다.

3. Context (입력 정보)
[스타일]: ##input
[가사 주제]: ##input
[가사 언어]: ##input
[참고 자료]: ##input

4. Output Format (출력 형식)
## 곡 제목 (Title)
[제목 제안 1]
[제목 제안 2]

## 장르 (Genre)
[스타일과 재즈가 결합된 구체적인 장르. 예: Lofi Jazz Pop, Acoustic Swing Ballad, Bossa Nova Folk]

## Music Style Prompt (English)
[200자 이내. A brief, evocative description for a composer, focusing on instrumentation, tempo, mood, and key harmonic features. (e.g., "A mellow, rainy-day jazz pop. Features a gentle Rhodes piano melody over brushed drums and a walking upright bass. Sophisticated 7th and 9th chords, with a slow, soulful vocal delivery. Tempo: 80 BPM.")]

## 가사 및 구성 (Lyrics & Composition)

[곡의 시작. 예: [Tempo: ♩= 75, Key: Eb Major]]
[인트로. 예: [Muted trumpet solo with a nostalgic vinyl crackle sound. Piano plays gentle, spacious Ebmaj7 - Abmaj7 chords.]]

[Verse 1]

[가사 첫 번째 줄]
[가사 두 번째 줄]
[가사 세 번째 줄. 예: [Upright bass quietly enters, marking the root notes.]]
[가사 네 번째 줄]

[Chorus]

[가사 첫 번째 줄]
[가사 두 번째 줄. 예: [Brushed drums add a subtle swing rhythm. Vocal harmony layers softly.]]
[가사 세 번째 줄]
[가사 네 번째 줄]

[간주 1. 예: [Piano takes a short, melodic solo, using bluesy grace notes.]]

[Verse 2]

[가사 첫 번째 줄]
[가사 두 번째 줄]
[가사 세 번째 줄. 예: [Dynamics build slightly. A soft string pad swells in the background.]]
[가사 네 번째 줄]

[Chorus]

[가사 첫 번째 줄]
[가사 두 번째 줄. 예: [Fuller arrangement. Drums are more active, bass walks more confidently.]]
[가사 세 번째 줄]
[가사 네 번째 줄]

[Bridge]

[가사 첫 번째 줄. 예: [Music suddenly becomes sparse. Key change to C minor. Vocal is whispery.]]
[가사 두 번째 줄]
[가사 세 번째 줄. 예: [Crescendo builds. Drums use light cymbal rolls.]]
[가사 네 번째 줄]
[악기 솔로. 예: [Tenor saxophone solo, expressive and blues-infused, over the Chorus chords.]]

[Chorus]

[가사 첫 번째 줄. 예: [Peak dynamic of the song. Vocals are powerful and emotive.]]
[가사 두 번째 줄]
[가사 세 번째 줄]
[가사 네 번째 줄]
[아웃트로. 예: [Piano riff from the intro returns. Fades out slowly with the vinyl crackle...]]
```


## [2.Music Style & Lyric 제작] 제작 요청 prompts 예시
* 참고 내용은 스토리만 있다면 아무거나 넣어도 됩니다.
```
- 스타일: 카페에서 플레이하기 좋은 보사노바 재즈 장르
- 가사언어: 영문
- 가사 스타일: 감성적이고 철학적인 장르. 자세한 인물묘사는 제외.
- 길이: 5분 이상

[참고 내용]
1. 총괄 컨셉 및 타겟

컨셉: '가장 차가운 존재가 가장 따뜻한 마음을 배우다'
핵심 메시지: 기술의 상징인 로봇이 야생에서 생존하며 동물들과 교감하고, '엄마'가 되어가는 과정을 통해 보여주는 생명과 관계의 소중함.
타겟:
주요 타겟: 자녀에게 좋은 책을 읽어주고 싶은 30-40대 부모
확장 타겟: 따뜻하고 감동적인 스토리를 좋아하는 성인 독자, AI와 공존에 대해 생각해보는 것을 좋아하는 10-20대

2. 유튜브 쇼츠 영상 시나리오 (A안)
"만약 AI 로봇이 야생의 엄마가 된다면?" 이라는 자극적인 질문으로 시작해 감성적인 
**이하 전체 컨텐츠 내용**

```


## [3. 추가 곡 생성] Prompts 예시
```
다른 제목과 가사로 추가 작성
- 보사노바 재즈 장르안에서 다른 스타일로 베리에이션.
```


## [5.Music Style & Lyric Output으로 곡 생성] Prompts
```
Style Prompts

A deeply melancholic and sparse Bossa Nova. Features a classic nylon guitar playing with heavy 'saudade,' soft brushes, and a resonant upright bass. A breathy, almost somber female vocal sings a nostalgic, philosophical lyric.
```
```
Lyric Prompts (곡 진행 설명은 반드시 대괄호[]로 작성. / 허밍, 랩, 나레이션은 소괄호()로 작성.)

[Verse 1] I trace the sand, a cold precise machine, The island's quiet, muted, and serene. My memory banks hold maps of sky and stone, But not this ache, of being here alone. My purpose was to learn, observe, survive, But not to feel this... terribly alive. I miss a sound, a call, a tiny beat, A presence that made my design obsolete.

...중략...

[Instrumental Solo] [A long, thoughtful Nylon Guitar solo takes center stage. The melody is expressive and filled with longing, supported only by the soft brush strokes and the deep, pulsing upright bass. 64 bars]

[Bridge] A machine should not remember, should not grieve. A machine should just perform, and then just leave. But my hard drive's full of sunset colors, bright, The feeling of a small head in the night. This isn't data, this is something else, A story that the quiet ocean tells. I am no longer just a sum of parts, But this collection of two broken hearts.

...중략...

[Outro] [Guitar plays the final chords very slowly, letting them ring out] The love you programmed... [Brushes fade away] ...into me. [A single, final bass note] [Silence]
```


## [7.Loop 용 Image 생성]Prompts 예시
```
Gemini에서 Image Prompt 분석 결과 사용하여 편집

"A digital painting in an impressionistic style of a young woman with short brown hair, wearing glasses and blue headphones. She is sitting comfortably in a wooden chair, holding a green mug, and smiling at the viewer. Next to her, a tabby cat sleeps peacefully on a book by a large window. The scene is filled with soft, cool lighting, primarily blues and greens, creating a cozy and peaceful atmosphere. Oil painting texture."
```


## [8. Image 첨부하여 Loop 용 Movie Prompts 생성] Prompt 예시
```
첨부된 이미지를 분석하여 movie prompt 작성.

- 커피잔은 가만히 들고만 있는다.
- 잔잔한 재즈음악에 맞춰서 리듬을 타는 여인
- 고양이는 잠을 자면서 꿈을 꾸는듯 미세한 움직임만 보인다.
```

## [9.Loop 영상 생성] Prompt 예시
- Image to Video 로 생성
- Start Frame과 End Frame에 동일한 이미지 삽입
```
Late afternoon sunlight streams through a large window, painting the exterior view in an abstract, warm orange glow. The interior of the apartment is predominantly deep, calming blue, creating a stark and artistic contrast between the two dominant colors.

A young woman, MIA (late 20s), is comfortably reclined in an armchair. She wears dark blue headphones and glasses. Her expression is serene and contemplative, eyes either softly closed or gazing distantly out the window with a dreamy look. She holds a steaming, deep blue coffee cup in her hands, but she is not drinking from it; she simply holds it, as if lost in thought, or as if time has paused.

Gentle, mellow jazz music plays, faintly audible to the viewer. Mia subtly sways or bobs her head, perhaps a slight shoulder roll, keeping a soft rhythm to the music. A faint, peaceful smile plays on her lips.

Near her, nestled on a book on her lap/side, is a tabby CAT, LUNA. Luna is deeply asleep, but shows subtle movements, as if dreaming. Her ears might twitch slightly, or her whiskers might quiver, indicating a dream-state. The warm orange light catches her fur, making it appear exceptionally soft and inviting.
```

## [10.Youtube 등록 상세 정보 생성] Prompt 예시
```
유튜브 동영상 제작 PD 및 마케팅 전문가로서 유튜브 동영상 등록 상세정보 작성.
사용자 의 최대 유입을 고려하여 작성.

등록 동영상은 [첨부된 음악]들로 구성된 유튜브 음악 플레이리스트 동영상입니다.
곡의 순서는 다음과 같습니다.

00:00 The Warmest Circuit (가장 따뜻한 회로)
05:40 Amor Mecânico (기계의 사랑)
11:56 An Unprogrammed Heart (프로그램에 없던 마음)
18:48 The Verdant Lullaby (초록빛 자장가)
24:34 Blue Circuitry (푸른 회로)
32:34 The Green Algorithm (초록빛 알고리즘)
37:39 Samba do Coração (심장의 삼바)
42:41 The Warmth in the Wires (그 전선 속의 온기)
48:09 Strings of Life (생명의 현)
55:20 A Ghost in the Bossa (보사노바 속의 유령) 
```