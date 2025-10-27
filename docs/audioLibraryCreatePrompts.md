## 작업 순서
### 1. 준비물 (다른 영상 제작의 컨텐츠 Storyboard 또는 Narration 대본 / Loop 사용할 Image)
### 2. [Gemini] Music Style & Lyric 제작
### 3. [Gemini] 추가 곡 생성 (4~5회 반복)
### 4. [Translate Google] 가사 검증
### 5. [Suno] Music Style & Lyric Output으로 곡 생성
### 6. [Pinterest or Midjourney] Image Reference Search
### 7. [Whisk or Midjourney] 9:16 Loop 용 Image 생성
### 8. [Gemini] Image 첨부하여 Loop 용 Movie Prompts 생성
### 9. [Flow or Midjourney] Loop 영상 생성


## [2.Music Style & Lyric 제작] Gems 설정
```
아이유같은 싱어송라이터 전문가로서 음악생성 prompt 작성.  참고자료가 스토리보드 형태일 경우 scene과 cut 구성은 무시하고 주제만 참고.

  - 스타일 : ##input  
  - 가사주제 : ##input
  - 가사 언어: ##input
  - 장르 : ##input


##출력 형식
- 곡 제목 (2개 이상 제안)
- 장르
- Music style prompt (200자내, 영문)
- 가사 (섹션 구분은 [Verse 1]와 같은 형식으로)
```


## [2.Music Style & Lyric 제작] 제작 요청 prompts 예시
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

## [8.Loop 영상 생성] Prompt 예시
- Image to Video 로 생성
- Start Frame과 End Frame에 동일한 이미지 삽입
```
Late afternoon sunlight streams through a large window, painting the exterior view in an abstract, warm orange glow. The interior of the apartment is predominantly deep, calming blue, creating a stark and artistic contrast between the two dominant colors.

A young woman, MIA (late 20s), is comfortably reclined in an armchair. She wears dark blue headphones and glasses. Her expression is serene and contemplative, eyes either softly closed or gazing distantly out the window with a dreamy look. She holds a steaming, deep blue coffee cup in her hands, but she is not drinking from it; she simply holds it, as if lost in thought, or as if time has paused.

Gentle, mellow jazz music plays, faintly audible to the viewer. Mia subtly sways or bobs her head, perhaps a slight shoulder roll, keeping a soft rhythm to the music. A faint, peaceful smile plays on her lips.

Near her, nestled on a book on her lap/side, is a tabby CAT, LUNA. Luna is deeply asleep, but shows subtle movements, as if dreaming. Her ears might twitch slightly, or her whiskers might quiver, indicating a dream-state. The warm orange light catches her fur, making it appear exceptionally soft and inviting.
```