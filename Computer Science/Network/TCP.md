## TCP(Transmission Control Protocol)

    인터넷에서 데이터를 신뢰성 있게 전달하기 위한 연결 지향형 프로토콜

    * 바이트 스트림 전송

    * 멀티캐스팅, 브로드캐스팅 지원X

<br>

### TCP 특징

1. 연결 지향(Connection-Oriented)
    - 데이터를 전송하기 전에 송신자와 수신자 간에 연결을 설정(SYN, ACK를 사용하는 3-way Handshake)
    
    - 연결 종료 시에도 연결 해제(4-way Handshake)를 수행

2. 신뢰성 있는 데이터 전송
    - 데이터가 손실되거나 순서가 바뀌지 않도록 보장
    - 오류 검출, 재전송, 데이터 흐름 제어를 통해 안정성을 제공

3. 전이중(full-duplex), 점대점(point to point)방식
    - 전이중
        - 전송이 양방향으로 동시에 일어날 수 있음을 의미

    - 점대점
        - 각 연결이 정확히 2 개의 종단점을 가지고 있음을 의미

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

    네트워크의 혼잡을 피하기 위해 송신측에서 보내는 데이터의 전송속도를 조절

#### 동작 방식

 - **송신자 중심의 제어**로, 네트워크 상태를 추정하여 데이터 전송 속도를 조절

 - 주요 알고리즘: **Slow Start**, **Congestion Avoidance**, **Fast Retransmit**, **Fast Recovery**

<br>

**혼잡 윈도우**(Congestion Window, cwnd)

    송신자가 네트워크 혼잡을 고려하여 설정하는 윈도우 크기입니다.

<br>

1. Slow Start (느린 시작)


2. Congestion Avoidance (혼잡 회피)


3. Fast Retransmit


4. Fast Recovery
