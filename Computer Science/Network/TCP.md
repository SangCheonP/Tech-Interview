## TCP(Transmission Control Protocol)

    인터넷에서 데이터를 신뢰성 있게 전달하기 위한 연결 지향형 프로토콜

    * 전송 계층

    * 바이트 스트림 전송

    * 멀티캐스팅, 브로드캐스팅 지원X

<br>

### TCP 특징

1. 연결 지향 (Connection-Oriented)
    - 데이터를 전송하기 전에 송신자와 수신자 간에 연결을 설정(SYN, ACK를 사용하는 3-way Handshake)
    
    - 연결 종료 시에도 연결 해제(4-way Handshake)를 수행

2. 신뢰성 있는 네트워크 (Reliable Network)
    - 데이터가 손실되거나 순서가 바뀌지 않도록 보장
    - 오류 검출, 재전송, 데이터 흐름 제어를 통해 안정성을 제공

3. 전이중(full-duplex), 점대점(point to point)방식
    - 전이중
        - 전송이 양방향으로 동시에 일어날 수 있음을 의미

    - 점대점
        - 각 연결이 정확히 2 개의 종단점을 가지고 있음을 의미

<br>

### Reliable Network를 보장하기 위한 4가지 문제

#### 1. 손실 (Loss)
- 네트워크 전송 중 패킷이 손실될 수 있음
    - ACK 기반 확인, 재전송(Retransmission)

#### 2. 순서 바뀜 (Out-of-Order Delivery)
- 여러 개의 패킷이 동시에 전송될 경우, 네트워크 경로가 다를 수 있어 수신자에게 순서가 뒤바뀐 상태로 도달
    - 시퀀스 번호(Sequence Number), 버퍼링(Buffering)

#### 3. 혼잡 (Congestion)
- 네트워크 경로에 트래픽이 과도하게 증가하여 데이터 전송 속도가 급격히 감소하거나 패킷 손실이 발생
    - 혼잡 제어(Congestion Control)

#### 4. 수신 측 과부하 (Receiver Overload)
- 수신자가 송신 속도를 따라잡지 못해 패킷 처리가 지연되거나 손실
    - 흐름 제어 (Flow Control), 수신자 버퍼링

<br>

### 흐름 제어(Flow Control)

    송신자가 수신자의 처리 능력을 초과하는 데이터를 보내지 않도록 조절하여 수신자의 버퍼 오버플로우를 방지

#### 동작 방식

 - 송신자는 윈도우 크기 내에서 데이터를 전송하고, 수신자로부터 ACK를 기다림

 - 수신자는 데이터를 수신하고, 버퍼에 여유 공간이 있으면 rwnd(Receive Window) 값을 유지하거나 증가시킴

 - 만약 버퍼가 가득 차면 rwnd 값을 0으로 설정하여 송신자에게 전송을 일시 중지하도록 요청합니다.

 <img src="https://camo.githubusercontent.com/a84918395b1352b40b4efc71b35f7f086d6a509ccf7d2ea711e02ded7ef90372/68747470733a2f2f74312e6461756d63646e2e6e65742f6366696c652f746973746f72792f323533463745343835373135454435463237">

<br>

### 혼잡 제어(Congestion Control)

     네트워크의 혼잡 상태를 예방하거나 완화하기 위해 송신 측에서 데이터 전송 속도를 조절하는 메커니즘

#### 동작 방식

 - **송신자 중심의 제어**로, 네트워크 상태를 추정하여 데이터 전송 속도를 조절

 - 주요 알고리즘: **Slow Start**, **Congestion Avoidance**, **Fast Retransmit**, **Fast Recovery**

<br>

**혼잡 윈도우**(Congestion Window, cwnd)

    송신자가 네트워크 혼잡을 고려하여 설정하는 윈도우 크기

<br>

<img src="https://t1.daumcdn.net/cfile/tistory/256E39425715F10103">

<br>

### 1. Slow Start (느린 시작)
 - 목적: 네트워크 초기에 전송 속도를 급격히 높여 혼잡을 발생시키는 것을 방지
 - 작동 방식:
   - 초기 cwnd 크기를 1 MSS(Maximum Segment Size)로 설정
   - 각 ACK(수신 확인 신호) 응답마다 cwnd 크기를 2배로 증가
   - **임계치**(ssthresh)에 도달하면 Congestion Avoidance 로 전환

### 2. Congestion Avoidance (혼잡 회피)
 - 목적: 네트워크가 혼잡 상태에 이르기 전에 전송 속도를 적절히 조절
 - 작동 방식:
    - cwnd 크기를 1씩 증가시켜 혼잡을 완화
    - 혼잡 신호(패킷 손실 또는 타임아웃)가 감지되면 cwnd 크기를 감소시킴
        - 중복 ACK (3개의 중복 ACK)
            - **cwnd를 절반으로 감소**시키고, 이후 **Congestion Avoidance**로 진입
            - ssthresh를 현재 cwnd의 절반 값으로 설정
            ```
            기존 cwnd = 16 MSS, ssthresh = 32 MSS
            중복 ACK 발생 → cwnd = 8 MSS, ssthresh = 8 MSS
            ```
        
        - 타임아웃
            - **cwnd를 1 MSS**로 줄이고, **Slow Start**로 전환
            - ssthresh를 현재 cwnd의 절반 값으로 설정
            ```
            기존 cwnd = 16 MSS, ssthresh = 32 MSS
            타임아웃 발생 → cwnd = 1 MSS, ssthresh = 8 MSS
            ```

### 3. Fast Retransmit (빠른 재전송)
 - 목적: 데이터 손실을 빠르게 복구하여 성능 저하를 줄임
 - 작동 방식:
    - 동일한 패킷에 대해 **3개의 중복 ACK**가 수신되면 데이터가 손실된 것으로 간주
    - 손실된 패킷을 즉시 재전송(타이머 만료를 기다리지 않음)

### 4. Fast Recovery
 - 목적: 손실된 패킷을 재전송한 후 네트워크 혼잡을 완화하고 빠르게 복구
 - 작동 방식:
    - 손실된 패킷을 재전송한 후 cwnd 크기를 절반으로 줄이고 Congestion Avoidance 단계로 이동
    - 네트워크 혼잡 상태를 복구하면서 성능을 최대한 유지