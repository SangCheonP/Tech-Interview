# TCP 3 & 4 way handshake

## 3 way handshake - 연결

    신뢰성있는 연결을 설정하기 위해 클라이언트와 서버 간에 이루어지는 3단계 절차

<br>

<img src="https://media.geeksforgeeks.org/wp-content/uploads/TCP-connection-1.png">

<br>

### 3 way handshake 동작 과정

1. 클라이언트 → 서버: 연결 요청
    - 클라이언트는 연결 요청 메시지(SYN, x)를 전송

2. 서버 → 클라이언트: 연결 요청 수락 및 응답
    - 서버는 클라이언트의 요청을 수락하며 응답으로 ACK(x + 1)과 SYN(y) 를 전송

3. 클라이언트 → 서버: 연결 완료
    - 클라이언트는 서버의 응답은 ACK(x+1)와 SYN(y) 패킷을 받고, ACK(y+1)를 서버로 보냄

```
1. 클라이언트 → 서버 : [SYN] SEQ = x
2. 서버 → 클라이언트 : [SYN, ACK] SEQ = y, ACK = x+1
3. 클라이언트 → 서버 : [ACK] SEQ = x+1, ACK = y+1
```

<br>

## 4 way handshake - 해제

    TCP 연결 종료를 위한 절차로, 한쪽에서 연결 종료를 요청하면 반대쪽도 이에 동의하는 절차를 거쳐 종료

<br>

<img src="https://media.geeksforgeeks.org/wp-content/uploads/CN.png">

<br>

### 4 way handshake 동작 과정

1. 클라이언트 → 서버(FIN): 연결 종료 요청
    - 클라이언트는 서버에게 연결을 종료한다는 FIN 플래그 전송

2. 서버 → 클라이언트(ACK): FIN 요청 확인
    - 서버는 FIN을 받고, 확인했다는 ACK를 클라이언트에게 보냄 (이때 모든 데이터를 보내기 위해 CLOSE_WAIT 상태가 됨)

3. 서버 → 클라이언트(FIN): 연결 종료 요청
    - 데이터를 모두 보냈다면, 연결이 종료되었다는 FIN 플래그를 클라이언트에게 보냄

4. 클라이언트 → 서버(ACK): 연결 종료 확인
    - 클라이언트는 FIN을 받고, 확인했다는 ACK를 서버에게 보냄 (아직 서버로부터 받지 못한 데이터가 있을 수 있으므로 일정 시간 동안 대기(TIME_WAIT)한 뒤 연결을 완전히 종료)

```
1. 클라이언트 → 서버 : [FIN] SEQ = x
2. 서버 → 클라이언트 : [ACK] ACK = x+1
3. 서버 → 클라이언트 : [FIN] SEQ = y
4. 클라이언트 → 서버 : [ACK] ACK = y+1
```

```
- 서버 -> ACK를 받은 직후 연결 종료(CLOSED)
- 클라이언트 -> TIME_WAIT가 끝나면 연결 종료(CLOSED)
```

<br>