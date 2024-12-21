# OSI 7계층 & TCP/IP

## OSI 7계층

    네트워크 통신을 계층적으로 나누어 설계한 모델.
    네트워크 시스템 간의 상호 운용성을 보장하고, 개발 및 문제 해결을 용이하게 하기 위해 제안됨.

<br>

<img src="https://s7280.pcdn.co/wp-content/uploads/2018/06/osi-model-7-layers-1.png">

<br>

### OSI 계층을 나눈 이유

    문제를 계층별로 구분하여 쉽게 파악하고, 필요한 부분만 수정할 수 있음. 이는 복잡한 네트워크를 효율적으로 관리하고 유지보수하는 데 매우 중요한 역할을 함.

<br>

### 1) 물리(Physical)

- 전기적 신호, 비트 스트림 전송
- 허브, 리피터, LAN 케이블

### 2) 데이터 링크(Data Link)

- 에러 검출, 데이터 프레임 생성 및 MAC 주소 관리
- 스위치, 브리지, Ethernet, PPP

### 3) 네트워크(Network)

- 경로 설정(라우팅), IP 주소를 통한 데이터 전송
- 라우터, IP, ARP, ICMP

### 4) 전송(Transport)

- 데이터 패킷 분할, 전송, 재조립. 신뢰성 보장(TCP) 또는 비연결성(UDP)
- TCP, UDP

### 5) 세션(Session)

- 세션 설정, 유지, 종료 관리. 데이터 동기화 및 확인
- API, Socket

### 6) 표현(Presentation)

- 데이터 변환(암호화, 복호화, 압축 등)
- JPEG, PNG, SSL/TLS

### 7) 응용(Application)

- 사용자와 네트워크 간 인터페이스 제공
- HTTP, FTP, SMTP, DNS

<br>

## TCP/IP

    인터넷을 포함한 네트워크에서 데이터를 주고받기 위한 표준 프로토콜 집합
    OSI 모델과 유사하게 계층 구조를 가지고 있으며, 네트워크 통신에서 가장 많이 사용되는 프로토콜

<br>

<img src="https://blog.kakaocdn.net/dn/bE1nli/btqIRNZyCgK/PE01DXdK3t4TnZ1kIoNj61/img.png">

<br>

### 1) 네트워크 액세스(Network Access)

- 데이터 프레임 생성, 물리적 전송
- Ethernet, Wi-Fi, LAN 케이블

### 2) 인터넷(Internet)

- 데이터의 목적지까지의 경로를 설정하고, 패킷을 전달
- IP(IPv4, IPv6), ICMP, ARP

### 3) 전송(Transport)

- 데이터 패킷 분할 및 재조립, 포트 번호 관리
- TCP, UDP

### 4) 응용(Application)

- 응용 서비스 제공 및 데이터 표현
- HTTP, FTP, SMTP, DNS