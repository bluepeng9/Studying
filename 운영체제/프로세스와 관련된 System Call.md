|               |                       |
|:--------------|:----------------------|
|  작성일          |  2023-04-10  |
|    분류         |      [Process](Process.md)                 |

# fork()
---
fork 시 자식 프로세스 pid == 0, 부모 pid > 0

# exec()
---
새로운 프로그램으로 덮어씌움

# wait()
---
프로세스 A 가 wait() System call 을 호출 하면
- 커널은 child가 종료될 때 까지 프로세스 A를 Sleep 시킨다 (block 상태)
- Child process 가 종료되면 커널은 프로세스 A를 깨운다 (ready 상태)

# exit()
---
- 자발적 종료
- 비자발적 종료
	- 부모 프로세스가 자식 프로세스를 강제 종료시킴
	- 자식 프로세스가 한계치를 넘어서는 자원 요청
	- 자식에게 할당된 task가 더 이상 필요하지 않음
- 키보드로 kill, break 등을 친 경우
- 부모가 종료하는 경우
	- 부모 프로세스가 종료하기 전에 자식들이 먼저 종료됨

# 관련 링크
---


# 출처
---
[9. 이화여자대학교 :: CORE Campus (ewha.ac.kr)](https://core.ewha.ac.kr/publicview/C0101020140325134428879622?vmode=f)