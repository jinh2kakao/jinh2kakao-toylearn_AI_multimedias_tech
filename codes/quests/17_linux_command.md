🧩 PowerShell 명령 연습 5개
① 폴더 이동 후 현재 위치 확인
cd C:\Commands
pwd

② 새 폴더 생성 후 목록 확인
cd C:\Commands
mkdir Projects
ls

③ 하위 폴더 생성 후 이동 및 현재 위치 확인
cd C:\Commands
mkdir Logs
cd Logs
pwd

④ 여러 개의 폴더를 차례로 만들고 목록 출력
cd C:\Commands
mkdir Data, Reports, Backup
ls

⑤ 특정 폴더로 이동한 뒤 상위 폴더 목록 확인
cd C:\Commands\Backup
cd ..
ls



 작업 폴더는 C:\Commands 입니다.

 ## PowerShell 명령 연습 수행

```
PS C:\Windows> cd ../..
PS C:\> mkdir commands


    디렉터리: C:\


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:44                commands


PS C:\> cd .\commands\
PS C:\commands> mkdir Projects


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:45                Projects


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:45                Projects


PS C:\commands> mkdir Logs


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:45                Logs


PS C:\commands> cd .\Logs\
PS C:\commands\Logs> pwd

Path
----
C:\commands\Logs


PS C:\commands\Logs> cd ../
PS C:\commands> mkdir Data, Reports, Backup


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:46                Reports
d-----      2025-11-06   오후 5:46                Backup


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports


PS C:\commands> cd .\Backup\
PS C:\commands\Backup> cd ..
PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports

```

---

### 🧠 PowerShell 명령 연습 문제
#### 문제 1
 C:\Commands 폴더로 이동한 뒤, 현재 작업 위치를 확인하세요.

#### 답 1
```
PS C:\commands> cd ../..
PS C:\> ls


    디렉터리: C:\


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                commands
d-----      2025-11-06  오전 11:13                Develops
d-----      2019-12-07   오후 6:14                PerfLogs
d-r---      2025-10-30  오후 12:38                Program Files
d-r---      2025-09-09  오전 10:42                Program Files (x86)
d-----      2024-01-10  오전 10:18                Temp
d-r---      2025-08-11   오후 3:26                Users
d-----      2025-09-24  오후 12:57                Voiceover
d-----      2025-10-30  오전 11:43                Windows


PS C:\> cd .\commands\
PS C:\commands> pwd

Path
----
C:\commands


PS C:\commands>
```


#### 문제 2
 C:\Commands 폴더 안에 Test라는 새 폴더를 만들고, 폴더 목록을 확인하세요.

#### 답 2
```
PS C:\commands> mkdir Test


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                Test


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports
d-----      2025-11-06   오후 5:49                Test


PS C:\commands>
```


#### 문제 3
 C:\Commands 안에 Notes 폴더를 만든 뒤, 해당 폴더로 이동하고 현재 위치를 확인하세요.

#### 답 3
```
PS C:\> cd .\commands\
PS C:\commands> mkdir Notes


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:50                Notes


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports
d-----      2025-11-06   오후 5:49                Test


PS C:\commands> cd .\Notes\
PS C:\commands\Notes> pwd

Path
----
C:\commands\Notes
```


#### 문제 4
 C:\Commands 폴더 안에 Images, Videos, Docs 세 개의 폴더를 한 번에 만들고, 생성된 폴더들을 확인하세요.

#### 답 4
```
PS C:\commands\Notes> cd ../
PS C:\commands> mkdir Images, Videos, Docs


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:52                Images
d-----      2025-11-06   오후 5:52                Videos
d-----      2025-11-06   오후 5:52                Docs


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:52                Docs
d-----      2025-11-06   오후 5:52                Images
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports
d-----      2025-11-06   오후 5:49                Test
d-----      2025-11-06   오후 5:52                Videos
```


#### 문제 5
 C:\Commands 안의 Docs 폴더로 이동한 뒤, 상위 폴더(C:\Commands)로 돌아가서 폴더 목록을 다시 확인하세요.

#### 답 5
```
PS C:\commands> cd ../..
PS C:\> cd C:\Commands\Docs
PS C:\Commands\Docs> cd ..
PS C:\Commands> ls


    디렉터리: C:\Commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:46                Backup
d-----      2025-11-06   오후 5:46                Data
d-----      2025-11-06   오후 5:52                Docs
d-----      2025-11-06   오후 5:52                Images
d-----      2025-11-06   오후 5:45                Logs
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:45                Projects
d-----      2025-11-06   오후 5:46                Reports
d-----      2025-11-06   오후 5:49                Test
d-----      2025-11-06   오후 5:52                Videos


PS C:\Commands>
```