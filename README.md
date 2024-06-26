# 오픈소스SW개론(20243147안태혁)

#### 'top','ps','jobs','kill'명령어에 대한 설명

1.top
---
>**top란?**

'top' 명령어는 실시간으로 시스템의 프로세스와 리소스 사용 상태를 모니터링하는 도구입니다. 실행하면 주기적으로 화면을 갱신하면서 현재 실행 중인 프로세스, CPU 사용률, 메모리 사용량, 시스템 부하 등을 표시합니다.
* [https://blog.naver.com/dktmrorl/222416977486>](https://terms.naver.com/entry.naver?docId=4125861&cid=59321&categoryId=59321)
  
1-1.형식
---
```github
top
```

1-2.옵션
---
* shift + p : CPU 사용률이 높은 프로세스 순서대로 표시

* shift + m : 메모리 사용률이 높은 프로세스 순서대로 표시

* shift + t : 프로세스가 돌아가고 있는 시간 순서대로 표시

* k : 프로세스  kill  - k 입력 후 종료할 PID 입력 signal을 입력하라고 하면 kill signal인 9를 입력

* a : 메모리 사용량에 따라 정렬

* b : Batch 모드 작동

* c : 명령행/프로그램 이름 토글

* d : 지연 시간 간격은 다음과 같다. -d ss. tt (seconds.tenths)

* h : 도움말 

* H : 스레드 토글

* i : 유휴 프로세스 토글

* m : VIRT/USED 토글

* M : 메모리 유닛 탐지

* n : 반복 횟수 제한 : -n number

* p : PID를 다음과 같이 모니터 : -pN1 -pN2 ... or -pN1, N2 [, ...] 

* s : 보안 모드 작동

* S : 누적 시간 모드 토글

* u : 사용자별 모니터링 : u somebody

* U : 사용자별 모니터링 : U somebody

* u : 입력한 유저의 프로세스만 표시  which u


1-3.세부 정보
---
![image](https://github.com/dksxogur/2024-1/assets/170289986/8fc7eeb4-7ae4-43f6-9598-53211af6849c)
  1.시스템 정보
  
  * 08:21:37 : 현재 시스템 시간이 08시 21분 37초임을 나타냅니다.
    
  * up 5 min : 시스템이 부팅된 지 5분이 지났음을 의미합니다.
    
  * 0 users : 현재 시스템에 로그인한 사용자가 없음을 의미합니다.
    
  * load average: 0.01, 0.14, 0.08 : 시스템의 부하 평균을 나타냅니다. 이 값들은 각각 1        분, 5분, 15분 동안의 평균 부하를 나타냅니다. 이 값이 낮을수록 시스템이 덜 바쁘다는        것 을 의미합니다.

     
  2.작업 정보
  
  * 2 total : 현재 총 2개의 작업(프로세스)이 실행 중임을 나타냅니다.
    
  * 1 running : 그 중 1개의 작업이 실행 상태임을 나타냅니다.
    
  * 1 sleeping : 그 중 1개의 작업이 대기(수면) 상태임을 나타냅니다.
    
  * 0 stopped : 정지된 작업이 없음을 의미합니다.
    
  * 0 zombie : 좀비 프로세스가 없음을 의미합니다.

    
  3.CPU 상태
  
  * 0.3 us : 사용자(user) 영역에서 소비한 CPU 시간 비율 (0.3%).
    
  * 0.1 sy : 시스템(kernel) 영역에서 소비한 CPU 시간 비율 (0.1%).
    
  * 0.0 ni : 우선순위가 변경된 사용자 프로세스가 소비한 CPU 시간 비율 (0.0%).
    
  * 99.6 id : 유휴 상태에서 소비한 CPU 시간 비율 (99.6%).
    
  * 0.0 wa : I/O 대기 상태에서 소비한 CPU 시간 비율 (0.0%).
    
  * 0.0 hi : 하드웨어 인터럽트에서 소비한 CPU 시간 비율 (0.0%).
    
  * 0.0 si : 소프트웨어 인터럽트에서 소비한 CPU 시간 비율 (0.0%).
    
  * 0.0 st : 가상화 환경에서 다른 가상 머신이 사용하는 시간 비율 (0.0%).

    
  4.메모리 상태
  
  * 3812.1 total : 총 3812.1 MiB의 물리 메모리를 나타냅니다.
    
  * 2407.9 free : 사용 가능한 메모리가 2407.9 MiB임을 나타냅니다.
    
  * 591.7 used : 현재 사용 중인 메모리가 591.7 MiB임을 나타냅니다.
    
  * 812.4 buff/cache : 버퍼 또는 캐시로 사용되는 메모리가 812.4 MiB임을 나타냅니다.

    
  5.스왑 메모리 상태
  
  * 1024.0 total : 총 1024.0 MiB의 스왑 공간을 나타냅니다.
    
  * 1024.0 free : 사용 가능한 스왑 공간이 1024.0 MiB임을 나타냅니다.
    
  * 0.0 used : 현재 사용 중인 스왑 공간이 0.0 MiB임을 나타냅니다.
    
  * 2997.6 avail Mem : 현재 시스템에서 사용할 수 있는 메모리가 2997.6 MiB임을 나타냅니다.


2.ps
---
>**ps란?**

'ps'명령어는 현재 싱행중인 프로세스의 스냅샷을 보여줍니다. 다양한 옵션을 사용하여 특정 프로세스, 사용자, 전체 시스템의 프로세스를 확인할 수 있습니다.

2-1.형식
---
```github
ps [OPTIONS]
```

2-2.주요 옵션
---
* 'ps aux' : 모든 사용자와 관련된 모든 프로세스를 자세히 보여줍니다.

* 'ps -ef' : 유사한 방식으로 모든 프로세스를 보여주지만 BSD 스타일이 아닌 표준 UNIX형식으              로 출력합니다.

* 'ps -u [username]' : 특정 사용자가 소유한 프로세스만 표시합니다.



3.jobs
---
>**jobs란?**

‘jobs’명령어는 현재 쉘 세션에서 백그라운드에서 실행 중이거나 일시 중단된 작업의 목록을 표시합니다.각 작업에는 작업 번호가 할당되며, 이를 사용하여 작업을 제어할 수 있습니다.
* https://terms.naver.com/entry.naver?docId=4125682&cid=59321&categoryId=59321
  
3-1.형식
---
```github
jobs [옵션][작업번호]
```

3-2.주요 옵션
---
  * '-l' 옵션 : 프로세스 ID와 함께 잡 목록을 출력합니다.
  
  * '-n' 옵션 : 마지막로 알림 이후 변경된 잡만 출력합니다.
  
  * '-p' 옵션 : 잡의 프로세스 ID만 출력합니다.
  
  * '-r' 옵션 : 실행 중인 잡만 출력합니다.
  
  * '-s' 옵션 : 중지된 잡만 출력합니다.

3-3.백그라운드 작업 상태값
---
  * Running : 작업이 계속 진행중임
  
  * Done : 작업이 완료되어 0을 반환

  * Done(code) : 작업이 종료되었으며 0이 아닌 코드를 반환

  * Stopped : 작업이 일시 중단
  
  * Stopped(SIGTSTP) : SIGTSTP시그널이 작업을 일시 중단
  
  * Stopped(SIGSTOP) : SIGSTOP시그널이 작업을 일시 중단
  
  * Stopped(SIGTTIN) : SIGTTIN시그널이 작업을 일시 중단
  
  * Stopped(SIGTTOU) : SIGTTOU시그널이 작업을 일시 중단


4.kill
---
>**kill이란?**

‘kill’명령어는 특정 프로세스에 신호를 보내어 종료시키거나 제어할 수 있는 도구입니다. 기본적으로 ‘SIGTERM’신호를 보내어 프로세스를 정상적으로 종료하도록 요청합니다. 필요에 따라 다른 신호를 보낼 수 있습니다.
* https://terms.naver.com/entry.naver?docId=4125687&cid=59321&categoryId=59321

4-1.형식
---
```github
kill [OPTIONS] [PID]
```

4-2.주요 옵션
---
  * '-l' :	모든 시그널 목록을 표시합니다.
  
  * '-s' :	지정한 시그널을 보냅니다.
  
  * '-9' :	SIGKILL 시그널을 보내어 강제 종료합니다.
  
  * '-15' :	SIGTERM 시그널을 보내어 정상 종료를 요청합니다.

4-3.주요 시그널
---
  * 'SIGHUP' :	세션 종료 시그널
  
  * 'SIGINT' :	인터럽트 시그널
  
  * 'SIGKILL' :	강제 종료 시그널
  
  * 'SIGTERM' :	정상 종료 요청 시그널
  
  * 'SIGSTOP' :	프로세스 일시 정지 시그널
