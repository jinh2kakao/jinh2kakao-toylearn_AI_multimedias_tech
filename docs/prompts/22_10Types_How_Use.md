## 프롬프트 유형과 선택 이유
1. [핵심 기반] 3. 역할 부여 (Role-Playing)
선택 이유: 이 시나리오는 단순한 코드 조각이 아닌, '회의에서 수정 가능한', '구조가 명확한' 프로토타입을 요구합니다. AI에게 "신속한 프로토타이핑 전문 시니어 프론트엔드 개발자" 또는 "UX/UI 엔지니어" 역할을 부여해야 합니다.

효과: 이 역할을 통해 AI는 <div>와 <table>로만 코드를 짜는 것이 아니라, CSS Grid/Flexbox를 사용한 모던한 레이아웃, 재사용 가능한 CSS 클래스, 주석(comment)이 포함된 깔끔한 JS 코드를 생성합니다. 이는 "즉석에서 수정 요청을 반영"해야 하는 핵심 과제를 수행하는 데 필수적입니다.

2. [핵심 행동] 1. 지시형 (Instructional)
선택 이유: 상황이 긴급하며(오늘 오후 4시) 요구사항이 명확합니다(코드 생성). "HTML, CSS, JS 코드를 생성해 줘"라는 명확하고 직접적인 지시가 가장 효율적입니다.

효과: AI가 불필요한 설명을 생략하고, 사용자가 즉시 복사하여 .html 파일로 저장할 수 있는 '코드 블록'을 생성하는 데 집중하게 만듭니다.

3. [품질 제어] 4. 제약 조건 (Constraint-Based)
선택 이유: 이 시나리오의 핵심은 상충되는 요구사항을 하나의 결과물로 통합하는 것입니다. '제약 조건' 유형은 이 모든 요구사항을 AI에게 명확한 '스펙(Spec)'으로 전달하는 역할을 합니다.

효과: 프롬프트에 다음과 같은 구체적인 제약 조건을 명시합니다.

파일 구조: "단일 HTML 파일에 CSS와 JS를 <style>, <script> 태그로 내장(embed)할 것." (신속한 공유 및 실행)

스타일: "트렌디한 다크 모드(배경: #1e1e1e, 텍스트: #f0f0f0)를 기본으로 적용할 것." (디자인팀 요구 충족)

레이아웃: "직관적인 3단 레이아웃(좌: 영상 목록, 중: 메인 플레이어/버튼, 우: 타임스탬프 댓글)을 사용할 것." (기획팀 요구 충족)

컴포넌트: "좌측 영상 목록은 '데이터 밀집형 테이블'(상태, 제목, 업로더)로 구현할 것." (운영팀 요구 충족)

기능: "승인/반려 버튼 클릭 시 alert 발생, 댓글 '제출' 시 목록에 추가되는 기본 JS 기능 포함." (인터랙션 시연)

## 작성 위해 추가 필요 요건
이 챌린지는 프론트엔드 개발자(수강생)가 스스로 기획자가 되어 모호한 요구사항을 구체화하는 능력을 훈련합니다. AI에게 정확한 지시를 내리기 위해 개발자가 다음과 같이 모호한 용어를 직접 구체화하여 프롬프트에 포함시켜야 합니다.

"직관적인 UI" (기획팀): 개발자가 이를 '3단 레이아웃' 또는 '헤더-바디 구조' 등으로 스스로 해석하여 AI에게 지시해야 합니다.

"데이터 밀집형 테이블" (운영팀): 개발자가 테이블에 들어갈 구체적인 컬럼명(예: Status, Title, Uploader, Date)을 직접 정의하여 AI에게 지시해야 합니다.

"타임스탬프 댓글 기능": 프로토타입 단계에서는 실제 영상 시간과 연동하는 복잡한 로직 대신, **'시간 입력칸(text) + 댓글 입력칸(text) + 제출 버튼'**의 단순한 형태로 구현하도록 구체화해야 합니다.

결론: AI에게 추가로 물어볼 필요 없이, 개발자(사용자)가 이 모호함을 해결한 '명확한 지시'를 프롬프트에 담아내는 것이 이 챌린지의 핵심입니다.

## 가상 문제 상황
제시해주신 상황(멀티미디어 기업, 업무용 웹페이지 요청, 의견 조율을 위한 프로토타입 작성)을 바탕으로 시나리오 챌린지를 생성했습니다.
수강생이 이 시나리오를 보고 "코딩/프로토타이핑" 관련 프롬프트 작성 능력을 훈련할 수 있도록 설계되었습니다.

🎬 시나리오 챌린지: 의견 조율을 위한 신속한 웹 프로토타입 개발
1. 가상 문제 상황
👤 페르소나: 멀티미디어 콘텐츠 기업 '네오스트림'의 프론트엔드 개발자 (3년 차)
🏙 배경:
귀사의 콘텐츠 운영팀으로부터 "사내 영상 리뷰 및 승인용 웹 대시보드" 제작을 긴급하게 요청받았습니다.
현재 기획서가 완성되지 않은 상태이며, 기획팀은 "직관적인 UI", 디자인팀은 "트렌디한 다크 모드", 운영팀은 "데이터 밀집형 테이블"을 각각 주장하며 의견이 좁혀지지 않고 있습니다.
💥 핵심 문제:
말로만 회의를 진행하다 보니 서로 상상하는 결과물이 달라 의사결정이 지연되고 있습니다.
오늘 오후 4시 회의 전까지, 실제로 작동하는 형태의 결과물이 없으면 프로젝트 착수가 무기한 연기될 위기입니다.
디자인 툴(Figma 등)로 그리기에는 시간이 부족하고, 버튼 클릭 등 인터랙션이 가능한 HTML/CSS 기반의 퍼블리싱 결과물을 보여줘야만 이해관계자들을 설득할 수 있습니다.
🎯 해결 과제:
요구사항(영상 플레이어 영역, 타임스탬프 댓글 기능, 승인/반려 버튼, 다크 모드 스타일)을 포함한 **단일 페이지 웹 프로토타입 코드(HTML, CSS, JS)**를 AI를 통해 즉시 생성하십시오.
이 코드는 회의 시간 내에 즉석에서 수정 요청을 반영할 수 있을 만큼 구조가 명확해야 합니다.
2. 훈련 초점 (힌트)
이 문제는 [코딩 및 프로토타입 생성 / 시각화] 능력을 평가
단순한 텍스트 생성이 아니라, 구체적인 UI/UX 요구사항을 구조화된 언어(코드)로 변환하는 프롬프트 엔지니어링 기술이 필요
## 문제 해결 프롬프트 
```
[역할 부여]
당신은 모던 프론트엔드(HTML, CSS Grid/Flexbox, ES6+ JS)에 능숙한 시니어 UI/UX 프로토타이핑 전문가입니다.

[과제]
'사내 영상 리뷰 및 승인 대시보드'의 긴급 프로토타입이 필요합니다. 3개 팀의 상충되는 요구사항을 모두 반영하여, 오늘 오후 4시 회의에서 즉시 시연할 수 있는 **단일 HTML 파일**을 생성해 주세요.

[핵심 제약 조건]

1.  **파일 구조 (필수):** **하나의 `.html` 파일** 안에 `<style>` 태그와 `<script>` 태그를 모두 내장(embed)하여 즉시 브라우저에서 열 수 있게 해주세요.
2.  **스타일 (디자인팀 요구):** **'트렌디한 다크 모드'**를 기본으로 적용합니다. (예: 배경 `#1a1e23`, 텍스트 `#f0f4f8`, 주요 버튼 `#007bff`)
3.  **레이아웃 (기획팀 요구):** **'직관적인 3단 그리드 레이아웃'**을 사용합니다.
    * `Column 1 (20%):` 영상 목록 (운영팀 테이블)
    * `Column 2 (55%):` 메인 영상 플레이어 및 승인/반려 버튼
    * `Column 3 (25%):` 타임스탬프 댓글
4.  **컴포넌트 1 (운영팀 요구):** `Column 1`에 **'데이터 밀집형 테이블'**을 만듭니다.
    * 컬럼: '상태' (예: Pending), '영상 제목', '업로더', '요청일'
    * 내용: 3~4개의 가상 데이터(dummy data)를 채워주세요.
5.  **컴포넌트 2 (핵심 기능):** `Column 2`에 다음을 배치합니다.
    * 상단: HTML5 `<video>` 태그 (회색 박스로 placeholder 처리)
    * 하단: 'Approve' (초록색), 'Reject' (빨간색) 버튼 2개.
6.  **컴포넌트 3 (핵심 기능):** `Column 3`에 **'타임스탬프 댓글'** 영역을 만듭니다.
    * 입력폼: '시간(Time)' 입력칸(예: 01:30), '댓글(Comment)' 텍스트 영역, '제출' 버튼
    * 리스트: 제출된 댓글이 쌓이는 `<ul>` 영역
7.  **기본 인터랙션 (JS):**
    * 'Approve' / 'Reject' 버튼 클릭 시 각각 `alert('승인되었습니다.')`, `alert('반려되었습니다.')`가 뜨게 합니다.
    * '제출' 버튼 클릭 시, '시간'과 '댓글'의 텍스트를 가져와 `[01:30] 좋은 의견입니다.`와 같은 형식으로 댓글 리스트(`<ul>`)에 `<li>`로 추가합니다.
8.  **코드 품질:** 회의 중 즉석 수정이 가능하도록 CSS 클래스 이름을 명확하게, JS 코드를 간결하고 주석이 달리게 작성해 주세요.
```

## 프롬프트 실행 결과
```
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>영상 리뷰 대시보드 - 프로토타입</title>
    <style>
        /* --- 기본 & 다크 모드 스타일 (디자인팀 요구) --- */
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
                Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
            background-color: #1a1e23; /* 어두운 배경 */
            color: #f0f4f8; /* 밝은 텍스트 */
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
            height: 100vh;
        }

        /* --- 3단 그리드 레이아웃 (기획팀 요구) --- */
        .dashboard-container {
            display: grid;
            grid-template-columns: 20% 55% 25%;
            gap: 20px;
            height: 95vh;
        }

        .panel {
            background-color: #2a2f37; /* 패널 배경 */
            border-radius: 8px;
            padding: 20px;
            overflow-y: auto;
        }

        h2 {
            border-bottom: 2px solid #007bff;
            padding-bottom: 10px;
            margin-top: 0;
        }

        /* --- Column 1: 영상 목록 테이블 (운영팀 요구) --- */
        .video-list-table {
            width: 100%;
            border-collapse: collapse;
        }
        .video-list-table th,
        .video-list-table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #444;
        }
        .video-list-table th {
            background-color: #3a3f47;
        }
        .status-pending { color: #ffc107; }
        .status-approved { color: #28a745; }

        /* --- Column 2: 메인 플레이어 --- */
        .video-placeholder {
            width: 100%;
            height: 400px; /* 임시 높이 */
            background-color: #444;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
            margin-bottom: 20px;
        }
        .action-buttons {
            display: flex;
            gap: 15px;
        }
        .btn {
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }
        .btn-approve { background-color: #28a745; color: white; }
        .btn-reject { background-color: #dc3545; color: white; }

        /* --- Column 3: 타임스탬프 댓글 --- */
        .comment-form { display: flex; flex-direction: column; gap: 10px; }
        .comment-form input,
        .comment-form textarea {
            background-color: #1a1e23;
            color: #f0f4f8;
            border: 1px solid #444;
            border-radius: 5px;
            padding: 10px;
        }
        .btn-submit { background-color: #007bff; color: white; }
        #comment-list {
            list-style-type: none;
            padding: 0;
            margin-top: 20px;
        }
        #comment-list li {
            background-color: #3a3f47;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        #comment-list li .time { font-weight: bold; color: #007bff; }
    </style>
</head>
<body>

    <div class="dashboard-container">
        <div class="panel" id="video-list">
            <h2>리뷰 요청 목록</h2>
            <table class="video-list-table">
                <thead>
                    <tr>
                        <th>상태</th>
                        <th>영상 제목</th>
                        <th>업로더</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="status-pending">Pending</td>
                        <td>신규 로고 애니메이션</td>
                        <td>디자인팀</td>
                    </tr>
                    <tr>
                        <td class="status-approved">Approved</td>
                        <td>2분기 실적 발표</td>
                        <td>IR팀</td>
                    </tr>
                    <tr>
                        <td class="status-pending">Pending</td>
                        <td>신제품 런칭 (v2)</td>
                        <td>마케팅팀</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div class="panel" id="main-player">
            <h2>영상 리뷰</h2>
            <div class="video-placeholder">(영상 플레이어 영역)</div>
            <div class="action-buttons">
                <button class="btn btn-approve" id="approve-btn">Approve (승인)</button>
                <button class="btn btn-reject" id="reject-btn">Reject (반려)</button>
            </div>
        </div>

        <div class="panel" id="comments">
            <h2>타임스탬프 댓글</h2>
            <form class="comment-form" id="comment-form">
                <input type="text" id="comment-time" placeholder="시간 (예: 01:30)">
                <textarea id="comment-text" rows="4" placeholder="리뷰 코멘트를 입력하세요..."></textarea>
                <button type="submit" class="btn btn-submit">제출</button>
            </form>
            <ul id="comment-list">
                </ul>
        </div>
    </div>

    <script>
        // --- 기본 인터랙션 JS (인터랙션 시연) ---

        // 1. 승인/반려 버튼 기능
        document.getElementById('approve-btn').addEventListener('click', function() {
            alert('승인되었습니다.');
        });

        document.getElementById('reject-btn').addEventListener('click', function() {
            alert('반려되었습니다.');
        });

        // 2. 타임스탬프 댓글 기능
        document.getElementById('comment-form').addEventListener('submit', function(event) {
            event.preventDefault(); // 폼 제출 기본 동작 방지

            // 입력값 가져오기
            const timeInput = document.getElementById('comment-time');
            const textInput = document.getElementById('comment-text');
            const commentList = document.getElementById('comment-list');

            const time = timeInput.value || "00:00"; // 기본값
            const text = textInput.value;

            if (!text) {
                alert('댓글 내용을 입력하세요.');
                return;
            }

            // 새 댓글 항목(li) 생성
            const newComment = document.createElement('li');
            newComment.innerHTML = `<span class="time">[${time}]</span> ${text}`;
            
            // 목록에 추가
            commentList.prepend(newComment); // 새 댓글을 맨 위에 추가

            // 입력칸 비우기
            timeInput.value = '';
            textInput.value = '';
        });
    </script>

</body>
</html>
```