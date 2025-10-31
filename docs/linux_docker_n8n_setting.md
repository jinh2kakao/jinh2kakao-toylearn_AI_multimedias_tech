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
4. docker에 n8n 설치 명령어 입력
```
docker run -it --rm --name n8n -p 5678:5678 -e TZ=Asia/Seoul  n8nio/n8n
```
5. 