# 리눅스 명령어

- 사용해본 적 있는 명령어 위주로 정리
- 자세한 옵션 등은 정리하지 않음

|명령어|내용|사용법|비고|
|---|---|---|---|
|pwd|현재 위치하고 있는 경로 출력|pwd|print working directory|
|cd|작업 위치 바꾸기|ch [이동할 경로]|change directory|
|mv|파일 옮기기, 이름 바꾸기|mv [바꿀 파일] [바꿀 이름 or 경로]|move|
|cat|파일 출력|cat [파일명]| \|(pipe)나 >(redirection)과 결합하여 다른 파일 및 프로그램에 연결시킬 때 주로 사용|
|echo|화면에 텍스트 출력|echo [문자열]|>를 이용해 간단히 파일을 만들 때나 $를 이용해 변수 등을 확인할 때 주로 사용|
|whoami|현재 계정 확인|whoami|who am i|
|which|특정 명령어의 경로 확인|which [명령어]||
|locate|패턴에 맞는 파일을 찾음|locate [패턴]||
|sudo|현재 계정에서 root 계정의 권한을 빌려 명령 실행|sudo [명령어]||
|su|계정 전환|su [계정명]|계정명이 없으면 root로 전환|
|yum install|app 설치|yum install [패키지명]|ubuntu에서는 apt-get 사용|
|yum update|패키지 업데이트 작업 수행|yum update|- ubuntu에서는 apt-upgrade 사용 <br> - apt-update는 패키기 저장소만 업데이트됨|
|yum upgrade|- yum update -obsoletes와 같은 작업 수행 <br> - 더이상 사용되지 않는 파일이나 패키지를 삭제|yum upgrade||
|ls|현재 디렉토리에 있는 디렉토리 및 파일 리스트를 출력|ls|- ls [경로] : 특정 경로에 있는 파일 목록도 출력 가능 <br> - -a : 숨김파일 포함 모든 리스트를 출력하는 옵션 <br> -l : 파일의 권한 등 자세한 정보를 함께 출력 <br> - ls -al로 많이 사용|
|visudo|sudo 권한을 편집할 수 있음|[계정명]  ALL=(ALL) ALL|문법을 체크해주므로 /etc/sudoers를 직접 편집하는 것보다 안전하다고 함|
|shutdown|시스템 종료|shutdown|- -h : 즉시 종료 옵션 <br> - -r : 재시작|
|reboot|시스템 리부팅|reboot|- -p : power off, 시스템 종료 <br> - -f : 강제로 재부팅|
|halt <br> poweroff|시스템 종료|halt <br> poweroff|reboot와 같은 옵션 사용|
|logout <br> exit|계정 로그아웃|logout <br> exit|시스템을 종료하지 않고 사용자 계정만 로그아웃|
|ifconfig|네트워크 설정 정보 확인|ifconfig|Network Manager에서 설정한 정보는 출력되지 않음|
|ip addr show|네트워크 설정 정보 확인|ip addr show|show 생략 가능|
|ping|패킷을 보내 대상 컴퓨터의 네트워크 상태를 확인|ping [목적지 주소]|- paket internet groper <br> - -c : 보내는 패킷 수 지정 <br> - -s : 보내는 패킷 길이 지정|
|nslookup|도메인 주소로 IP 조회|nslookup [도메인]|- RedHat 계열은 명령어가 bind-utils 패키지 내에 포함되어 있음 <br> - DNS 서버에서 DNS를 쿼리해 결과를 출력해주는 것 <br> - 서버의 네트워크가 제대로 설정됐는지 확인하는 용도로 사용|
|adduser <br> useradd|사용자 추가|adduser [계정명] <br> useradd [계정명]|root 권한을 가진 사용자만 사용 가능|
|history|명령어 사용 내역 확인|history|!번호 : 번호에 해당하는 명령어 재사용|
|hostnamectl|호스트명 등 관련된 정보 출력|hostnamectl|hostnamectl status와 같은 결과|
|hostnamectl set-hostname|호스트명 변경|hostnamectl set-hostname [변경할 호스트명]|호스트명을 영구히 변경|
|alias|별명 지정|alias [명령어]="[별명]"|재부팅 후에도 사용하려면 ~/.bashrc에 저장해야 함|
|source|파일 내 명령어 실행|source [파일명]|- bash의 명령어 <br> - .bashrc, .bash_profile 수정 이후 적용할 때 주로 사용|
|netstat|네트워크 연결 상태 확인|netstat|- -a : 모든 소켓 표시 <br> - -p : TCP 소켓 표시 <br> - -l : 연결 대기 상태인 소켓 표시|


# 리눅스 폴더

|폴더명|내용|
|---|---|
|/|최상위 디렉토리 (root)|
|/bin|- binary의 약자 <br> - 기본적인 명령어 실행 파일을 담은 디렉토리 <br> - cp, mv, mkdir, cat, rm 등|
|/boot|부팅 이미지 부팅시에 필요한 파일을 담은 디렉토리|
|/dev|- 물리적인 장치(시스템 디바이스)를 파일화하여 관리하는 디렉토리 <br> - 하드 디스크 장치 파일 등|
|/etc|시스템 환경 설정 파일 및 부팅과 관련된 스크립트 파일을 담은 디렉토리|
|/home|개인 사용자들의 홈 디렉토리|
|/root|루트 사용자의 홈 디렉토리|
|/lib|- library의 약자 <br> - 커널 모듈을 포함한 각종 라이브러리가 저장되어 있는 디렉토리|
|/mnt|CD-ROM, 하드 디스크, 네트워크 파일 시스템 등을 마운트할 때 사용하는 디렉토리|
|/proc|- 가상 파일 시스템 <br> - 메모리에 올라간 작업(프로세스)의 상태 정보, 하드웨어 정보, 기타 시스템 정보 등을 담은 디렉토리|
|/opt|응용프로그램 설치를 위해 사용되는 디렉토리|
|/tmp|- 임시 저장 디렉토리 <br> - 각종 프로그램 및 프로세스 작업시 임시로 생성되는 파일을 저장하는 디렉토리 <br> - 공용 디렉토리로 모든 사용자에게 읽기 쓰기 허용 <br> Sticky bit 설정으로 파일 소유자만 자신이 소유한 파일을 삭제할 수 있음|
|/sbin|- 시스템 관리를 위한 명령어가 저장된 디렉토리 <br> - ifconfig, ethtool, halt 등|
|/usr|- 시스템 운영에 필요한 명령, 사용자 데이터, 응용 프로그램이 저장되는 디렉토리|
|/usr/bin <br> /usr/sbin|- /bin, /sbin에 들어있는 명령어를 제외한 명령어가 들어있는 디렉토리 <br> - 응용 프로그램의 명령어, wget 등으로 다운로드 받은 명령어가 들어 있는 디렉토리|
|/usr/local|로컬에서 응용 프로그램을 소스로 컴파일해 설치할 때 사용되는 장소|
|/var|- 시스템 운영 로그 파일, 메타 데이터 등 가변 자료를 저장하는 디렉토리 <br> - 메일 서버로 운영될 경우 하위 디렉토리에 메일이 저장됨|
|/lost+found|결함이 있는 파일에 대한 정보가 저장된 디렉토리|
|/media|CD-ROM, floppy 등을 마운트하기 위해 제공되는 디렉토리|
|/srv|사이트에서 생성되는 데이터를 저장하는 디렉토리|
|/sys|- 가상 파일 시스템인 sysfs에서 사용하는 디렉토리 <br> - hot plug 하드웨어 정보를 가지고 있는 디렉토리|
|/lib64|- 64비트용 리눅스를 설치하는 경우 생성되는 디렉토리 <br> - 64비트 기반의 라이브러리를 담은 디렉토리|
|/run|- 부팅 이후 동작중인 프로세스의 런타임 데이터가 저장되는 디렉토리 <br> - 프로세스 ID 파일, 락 파일 등이 생성되며 재부팅시 다시 생성됨|
