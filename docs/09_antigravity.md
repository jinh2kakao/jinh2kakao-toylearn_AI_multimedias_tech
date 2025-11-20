# docker의 컨테이너를 remote로 실행하는 방법
```
apt-get update && apt-get install -y procps
```
# preview 안되는 문제 해결방법
```
cd docs/vibecodings/02_publishings_createsite && python3 -m http.server 8080
```


## 1단계: .vscode/launch.json 생성 (버튼 연결)
이 파일은 IDE의 "실행 및 디버그(Run & Debug)" 탭과 F5 키를 제어합니다.

.vscode 폴더 안에 launch.json 파일을 만듭니다. (이미 있다면 엽니다.)

아래 코드를 붙여넣습니다.

JSON

```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Antigravity Preview (Chrome)",
            "type": "pwa-chrome",
            "request": "launch",
            "url": "http://localhost:8080", 
            "webRoot": "${workspaceFolder}/docs/vibecodings/02_publishings_createsite",
            // 중요: 미리 만들어둔 서버 실행 Task를 먼저 실행하고 브라우저를 엽니다.
            "preLaunchTask": "Run Web Server" 
        },
        {
            "name": "Simple Browser (Inside IDE)",
            "type": "simple-browser",
            "request": "launch",
            "url": "http://localhost:8080",
            "preLaunchTask": "Run Web Server"
        }
    ]
}
```

핵심 원리: "preLaunchTask": "Run Web Server" 부분이 핵심입니다. 미리보기 버튼을 누르면 자동으로 아까 만든 Python 서버부터 켜고 브라우저를 연결합니다.

## 2단계: tasks.json 미세 조정 (백그라운드 설정)
launch.json이 서버를 켤 때, 서버가 터미널을 점유해버려서 브라우저가 안 열리는 것을 막기 위해 isBackground 패턴을 확실히 해줍니다.

아까 작성하신 tasks.json을 아래 내용으로 업데이트 해주세요. (problemMatcher 부분 추가가 핵심입니다.)

JSON
```
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Run Web Server",
            "type": "shell",
            "command": "python3 -m http.server 8080",
            "options": {
                "cwd": "${workspaceFolder}/docs/vibecodings/02_publishings_createsite"
            },
            "isBackground": true, // 백그라운드 실행
            "presentation": {
                "reveal": "silent",
                "panel": "dedicated"
            },
            // 서버가 "준비됨"을 IDE가 인식하게 하는 정규식 패턴
            "problemMatcher": {
                "owner": "python",
                "fileLocation": ["relative", "${workspaceFolder}"],
                "pattern": {
                    "regexp": "^(.*)$"
                },
                "background": {
                    "activeOnStart": true,
                    "beginsPattern": "Serving HTTP", 
                    "endsPattern": "Serving HTTP"   
                }
            }
        }
    ]
}
```

### 🏁 사용 방법 (이제 이렇게 쓰세요)
이제 터미널 명령어는 잊으셔도 됩니다.

방법 A: F5 키 사용 (가장 추천)

키보드에서 F5를 누릅니다 (또는 좌측 '실행 및 디버그' 탭에서 ▶️ 버튼 클릭).

서버가 자동으로 켜지고, 새 브라우저 창(또는 탭)이 열리면서 화면이 바로 뜹니다.

방법 B: Antigravity Native Preview 버튼 만약 상단의 "Web Preview" 버튼을 계속 쓰고 싶으시다면, 서버를 자동 실행 시켜두면 됩니다. tasks.json의 options 아래에 다음 한 줄을 추가하면 IDE를 켤 때마다 서버가 알아서 켜집니다.

JSON
```
"runOptions": { "runOn": "folderOpen" }
```
이렇게 하면 로그인하자마자 우측 상단 Web Preview 버튼이 활성화되어 있을 것입니다.