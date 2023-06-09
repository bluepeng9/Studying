- 작성일: 2023-04-30
- 태그: 
- 분류:
	- [TCP](TCP.md)
- 관련 노트:
---

신뢰할 수 있는 프로토콜로, 현재는 대부분 TCP를 사용한다

---
# 연결 지향

## TCP 3 way handshake (가상 연결)

```text
Client                          Server
|                              |
|  1. SYN (seq=X)              |
|--------------------------->  |
|                              |
|  <---------------------------|  2. SYN-ACK (seq=Y, ack=X+1)
|                              |
|  3. ACK (seq=X+1, ack=Y+1)   |
|--------------------------->  |
|                              |

SYN: 접속 요청
ACK: 요청 수락
참고: ACK와 함께 데이터 전송 가능
```

1. 클라이언트가 SYN 패킷을 서버에 보낸다.
	-  이 때 X는 랜덤이다.
2. 서버가 메시지를 받으면, ACK 패킷과 함께 SYN 메시지를 보낸다.
	-  이 때 Y는 랜덤이다.
3. 클라이언트가 서버의 메시지를 받고 ACK 패킷을 보낸다.



---
# 데이터 전달 보증


```text
Client                        Server
| 1                            |
|------------------------->    |
|                              |
|                          2   |
|    <-------------------------|
|                              |
|                              |
```

1. 데이터 보냄
2. 데이터 잘 받았음

---

# 순서 보장

```text
Client                        Server
| 1. Send packets 1, 2, 3 in order |
|------------------------->        |
|                                  |
|                                  | 2. Packets 1, 3, 2 arrive in order
|                                  |
|                                  |
|          3. Resend from packet 2 |
|       <--------------------------|
|                                  |
|                                  |
```

1. 클라이언트가 패킷 1 2 3 순으로 보냄
2. 서버에 1 3 2 순으로 도착
3. 서버가 클라이언트에게 패킷 2 부터 다시 보내라고 요청


---
# Reference
- [모든 개발자를 위한 HTTP 웹 기본 지식 - 인프런 | 강의 (inflearn.com)](https://www.inflearn.com/course/http-%EC%9B%B9-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC)

---