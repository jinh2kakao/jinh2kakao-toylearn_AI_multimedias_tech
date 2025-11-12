## 01. Docker 설치
- 설치 URL: https://www.docker.com/
- Windows AMD64 설치

## 02. Ubuntu 설치
- 관리자 권한으로 Powershell 실행
- Powershell에 명령어 차례 대로 입력
```
> [Security.Principal.WindowsIdentity]::GetCurrent().Groups -contains 'S-1-5-32-544'

> dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
> dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
> wsl --update --web-download
> wsl --set-default-version 2
> wsl --status
> wsl --install
```
** 설치 안될 경우 CPU 가상화 확인
BIOS 메뉴에서 'Advanced(고급)', 'CPU Configuration(CPU 구성)', 'Security(보안)' 등의 탭을 찾아봅니다.
다음과 같은 이름의 옵션을 찾습니다.
Intel CPU: Intel Virtualization Technology (VT-x) 또는 Intel VT-d
AMD CPU: AMD-V, SVM (Secure Virtual Machine) Mode

## 03. Docker 실행
1. Docker 실행
2. Powershell 관리자 권한 실행
3. docker 실행 명령어 입력
```
docker run -d -p 8080:80 nginx
```
4. docker에 n8n 설치 명령어 입력. (재실행시에도 동일)
```
docker run -it --rm --name n8n -p 5678:5678 -e TZ=Asia/Seoul  n8nio/n8n

```
5. docker의 container에서 브라우저 실행.

6. n8n 실행확인.

7. https://codeindocker.com/securities/github/callback?code=4d4439684b3023ad9d3b 에서 yojulab_learn_n8ns_2025110511 다운로드 후 압축 해제

8. Powershell 관리자 권한 실행 (경로 이동: cd [이동경로])

9. Powershell 명령어 입력 및 실행 docker-compose --project-name yojulab_learn_n8ns up -d --build



# Mac OS setup
전문 개발자 입장에서 Intel 칩 기반 macOS 환경에 맞게 Docker 설치 및 실행 프로세스를 재구성해 드립니다.

Windows와 macOS는 운영체제 아키텍처가 근본적으로 다르기 때문에, 2번 항목(Ubuntu 설치)은 완전히 다른 방식으로 대체됩니다.

---

## 01. Docker 설치

1.  **설치 URL 접속**: [https://www.docker.com/](https://www.docker.com/)
2.  **Docker Desktop for Mac 다운로드**:
    * 사이트에서 'Docker Desktop' 다운로드 섹션으로 이동합니다.
    * macOS 버전을 선택할 때, **'Mac with Intel chip'** 버전을 다운로드해야 합니다. ('Apple chip' 버전은 M1, M2 등 ARM 기반 Mac용입니다.)
3.  **설치 진행**:
    * 다운로드한 `Docker.dmg` 파일을 엽니다.
    * Docker 아이콘을 `Applications` (응용 프로그램) 폴더로 드래그 앤 드롭하여 설치합니다.

---

## 02. Linux 환경 설정 (WSL 대체)

**이 단계는 macOS에서 필요하지 않습니다.**

* 제시해주신 2번 항목의 명령어(`dism.exe`, `wsl`, `Powershell`)는 **Windows 전용** 기능인 **WSL(Windows Subsystem for Linux)**을 활성화하고 설정하는 과정입니다.
* macOS용 Docker Desktop은 설치 시, macOS에 내장된 Hypervisor 프레임워크를 사용하여 **자체적으로 경량화된 Linux 가상 머신(VM)을 실행**합니다.
* 따라서 사용자가 별도로 Ubuntu나 Linux 배포판을 설치하거나, BIOS/EFI에서 가상화 옵션(Intel VT-x)을 활성화할 필요가 없습니다. (Intel Mac은 이미 기본 활성화되어 있습니다.)

**결론: 1번 Docker 설치만 완료하면, 2번 단계는 macOS에서 자동으로 처리됩니다.**

---

## 03. Docker 실행 및 컨테이너 구동

1.  **Docker 실행**:
    * `Applications` (응용 프로그램) 폴더에서 **Docker Desktop** 앱을 실행합니다.
    * 실행 후, 화면 상단 메뉴 막대에 고래 아이콘이 나타나고 "Docker Desktop is running" 상태가 될 때까지 잠시 기다립니다.

2.  **터미널(Terminal) 실행**:
    * Powershell 대신 macOS의 기본 터미널 앱을 사용합니다.
    * **실행 방법**: Finder > 응용 프로그램 > 유틸리티 > **터미널.app**을 실행하거나, Spotlight(Cmd + Space)에서 `Terminal`을 검색하여 실행합니다.

3.  **Nginx 컨테이너 실행**:
    * 터미널에 다음 명령어를 입력합니다. (Windows와 동일)
    ```bash
    docker run -d -p 8080:80 nginx
    ```
    * **확인**: 웹 브라우저에서 `http://localhost:8080`으로 접속했을 때 "Welcome to nginx!" 페이지가 보이면 성공입니다.

4.  **n8n 컨테이너 실행**:
    * 터미널에 다음 명령어를 입력합니다. (Windows와 동일)
    ```bash
    docker run -it --rm --name n8n -p 5678:5678 -e TZ=Asia/Seoul n8nio/n8n
    ```
    * **확인**: 웹 브라우저에서 `http://localhost:5678`으로 접속했을 때 n8n 초기 설정 화면이 보이면 성공입니다.

---

## 04. (참고) 실행 중인 컨테이너 확인

터미널에서 다음 명령어를 입력하면 현재 실행 중인 Docker 컨테이너 목록(nginx, n8n)을 확인할 수 있습니다.

```bash
docker ps
```

# VS CODE에서 remote 접속 방법
1. VS CODE에서 확장팩 설치
```
ms-vscode-remote.vscode-remote-extensionpack
```

2. Open a Remote Window (좌측 하단) 버튼 클릭하여 명령 팔레트 오픈

3. Attach to Running Contatainer 클릭하여 실행중인 컨테이너 확인

4. open folder하여 레포지토리 오픈

# VS code에서 live server 운영
ritwickdey.liveserver 확장팩 설치

# fast api 및 n8n, 포스트그릴 전체 설치 방법

1. [코인도커](https://codeindocker.com/)사이트에서 압축 파일 다운로드
 파일명: Learn n8n with FastAPI and PostgreSql with Vector

2. 다운받은 파일 압축해제

3. Powershell 관리자 권한 실행

4. 압축파일 경로로 이동
```
cd [압축파일 경로]
```

5. 명령어 넣고 실행
```
명령어

docker-compose --project-name yojulab_learn_n8ns up -d --build
```
