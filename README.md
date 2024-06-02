# 오픈소스SW개론(20243147안태혁)

#### 리눅스에서 프로세스와 작업을 관리하는 데 자주 사용되는 'top','ps','jobs','kill'명령어에 대해 설명합니다.

1.top
---
'top' 명령어는 실시간으로 시스템의 프로세스와 리소스 사용 상태를 모니터링하는 도구입니다. 실행하면 주기적으로 화면을 갱신하면서 현재 실행 중인 프로세스, CPU 사용률, 메모리 사용량, 시스템 부하 등을 표시합니다.
  
1-1.주요 기능
---
-시스템의 전체적인 상태를 실시간으로 모니터링

-CPU 및 메모리 사용량에 따른 프로세스 정렬

-특정 프로세스에 대해 자세한 정보 제공

1-2.사용 예시
---
![image](https://github.com/dksxogur/2024-1/assets/170289986/8fc7eeb4-7ae4-43f6-9598-53211af6849c)
  1.시스템 정보
    -08:21:37: 현재 시스템 시간이 08시 21분 37초임을 나타냅니다.
    
    -up 5 min: 시스템이 부팅된 지 5분이 지났음을 의미합니다.
    
    -0 users: 현재 시스템에 로그인한 사용자가 없음을 의미합니다.
    
    -load average: 0.01, 0.14, 0.08: 시스템의 부하 평균을 나타냅니다. 이 값들은 각각 1        분, 5분, 15분 동안의 평균 부하를 나타냅니다. 이 값이 낮을수록 시스템이 덜 바쁘다는        것 을 의미합니다.

     
  2.작업 정보
    -2 total: 현재 총 2개의 작업(프로세스)이 실행 중임을 나타냅니다.
    
    -1 running: 그 중 1개의 작업이 실행 상태임을 나타냅니다.
    
    -1 sleeping: 그 중 1개의 작업이 대기(수면) 상태임을 나타냅니다.
    
    -0 stopped: 정지된 작업이 없음을 의미합니다.
    
    -0 zombie: 좀비 프로세스가 없음을 의미합니다.

    
  3.CPU 상태
    -0.3 us: 사용자(user) 영역에서 소비한 CPU 시간 비율 (0.3%).
    
    -0.1 sy: 시스템(kernel) 영역에서 소비한 CPU 시간 비율 (0.1%).
    
    -0.0 ni: 우선순위가 변경된 사용자 프로세스가 소비한 CPU 시간 비율 (0.0%).
    
    -99.6 id: 유휴 상태에서 소비한 CPU 시간 비율 (99.6%).
    
    -0.0 wa: I/O 대기 상태에서 소비한 CPU 시간 비율 (0.0%).
    
    -0.0 hi: 하드웨어 인터럽트에서 소비한 CPU 시간 비율 (0.0%).
    
    -0.0 si: 소프트웨어 인터럽트에서 소비한 CPU 시간 비율 (0.0%).
    
    -0.0 st: 가상화 환경에서 다른 가상 머신이 사용하는 시간 비율 (0.0%).

    
  4.메모리 상태
    -3812.1 total: 총 3812.1 MiB의 물리 메모리를 나타냅니다.
    
    -2407.9 free: 사용 가능한 메모리가 2407.9 MiB임을 나타냅니다.
    
    -591.7 used: 현재 사용 중인 메모리가 591.7 MiB임을 나타냅니다.
    
    -812.4 buff/cache: 버퍼 또는 캐시로 사용되는 메모리가 812.4 MiB임을 나타냅니다.

    
  5.스왑 메모리 상태
    -1024.0 total: 총 1024.0 MiB의 스왑 공간을 나타냅니다.
    
    -1024.0 free: 사용 가능한 스왑 공간이 1024.0 MiB임을 나타냅니다.
    
    -0.0 used: 현재 사용 중인 스왑 공간이 0.0 MiB임을 나타냅니다.
    
    -2997.6 avail Mem: 현재 시스템에서 사용할 수 있는 메모리가 2997.6 MiB임을 나타냅니다.


2.ps
---
'ps'명령어는 현재 싱행중인 프로세스의 스냅샷을 보여줍니다. 다양한 옵션을 사용하여 특정 프로세스, 사용자, 전체 시스템의 프로세스를 확인할 수 있습니다.

2-1.주요 옵션
---
-'ps aux': 모든 사용자와 관련된 모든 프로세스를 자세히 보여줍니다.
-'ps -ef': 유사한 방식으로 모든 프로세스를 보여주지만 BSD 스타일이 아닌 표준 UNIX형식으로 출력합니다.
-'ps -u [username]': 특정 사용자가 소유한 프로세스만 표시합니다.



3.jobs
---
‘jobs’명령어는 현재 쉘 세션에서 백그라운드에서 실행 중이거나 일시 중단된 작업의 목록을 표시합니다.각 작업에는 작업 번호가 할당되며, 이를 사용하여 작업을 제어할 수 있습니다.

3-1.주요 기능
---
-백그라운드에서 실행 중인 작업 확인
-일시 중단된 작업 확인



4.kill
---
‘kill’명령어는 특정 프로세스에 신호를 보내어 종료시키거나 제어할 수 있는 도구입니다. 기본적으로 ‘SIGTERM’신호를 보내어 프로세스를 정상적으로 종료하도록 요청합니다. 필요에 따라 다른 신호를 보낼 수 있습니다.

4-1.주요 옵션
---
-‘kill [PID]’:지정한 프로세스 ID에 ‘SIGTERM’신호를 보냅니다.
-'kill -9 [PID]': 지정한 프로세스 ID에 SIGKILL 신호를 보내어 강제로 종료합니다.
-'kill -l': 사용 가능한 모든 신호의 목록을 표시합니다.
