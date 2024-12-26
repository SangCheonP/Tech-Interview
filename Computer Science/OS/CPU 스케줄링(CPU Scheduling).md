# CPU 스케줄링(CPU Scheduling)
## 스케줄링(Scheduling)
```
OS가 CPU를 여러 프로세스 사이에 효율적으로 할당하는 방법

* 오버헤드 ↓ / 사용률 ↑ / 기아 현상 ↓
```

<br>
<hr>

### 선점(preemptive) 스케줄링
```
현재 실행 중인 프로세스가 CPU를 사용하고 있을 때, 더 높은 우선순위의 프로세스가 도착하거나 특정 조건이 충족되면 현재 프로세스를 중단하고 CPU를 다른 프로세스에게 할당
```

#### 특징
- **실시간 시스템**에 자주 사용
- 더 높은 우선순위의 프로세스가 대기하는 시간을 줄임
- 문맥 교환(Context Switching)이 빈번하게 발생하므로 **오버헤드 증가**

#### 사용 사례
- Round Robin

<br>
<hr>

### 비선점(nonpreemptive) 스케줄링
```
CPU를 할당받은 프로세스는 작업을 완료할 때까지 계속 실행하며, 다른 프로세스가 CPU를 강제로 가져올 수 없음
```

#### 특징
- 문맥 교환(Context Switching)이 없으므로 **오버헤드가 적음**
- 우선순위가 높은 프로세스가 **대기할 가능성이 있음** (Convoy Effect)

#### 사용 사례
- FCFS (First-Come, First-Served)

<br>

## 주요 스케줄링 알고리즘
### FCFS (First-Come, First-Served)
```
프로세스가 도착한 순서대로 CPU를 할당
```

#### 단점
- Convoy Effect(긴 프로세스가 앞에 있을 경우 뒤 프로세스가 오래 기다림)

<br>
<hr>

### SJF (Shortest Job First)
```
실행 시간이 가장 짧은 프로세스를 먼저 실행

- 선점형 : 더 짧은 실행 시간의 프로세스가 도착하면 현재 프로세스를 중단
- 비선점형 : 실행 중인 프로세스를 중단하지 않음
```

#### 단점
- 프로세스의 실행 시간을 미리 알기 어려움

<br>
<hr>

### Priority Scheduling
```
우선순위가 높은 프로세스에 CPU를 할당

* 우선순위에 따라 선점형 또는 비선점형으로 동작
```

#### 단점
- 기아 문제(Starvation)
    - 우선순위가 낮은 프로세스가 **무한 대기**하는 현상
    - **에이징(Aging)**으로 해결 가능

#### 에이징 (Aging)
```
기아 문제(Starvation)를 방지하기 위한 기법으로, 오랫동안 대기 중인 프로세스의 우선순위를 점진적으로 증가시키는 방식
```

<br>
<hr>

### Round Robin (RR)
```
프로세스마다 일정한 Time Quantum(= Time Slice) 동안 CPU를 할당하고, 그 이후에 대기열의 다음 프로세스로 전환

* Time Quantum : 실행의 최소 단위 시간
```

#### 단점 : 
- Time Quantum ↑ : **FCFS**와 유사해짐
- Time Quantum ↓ : 문맥 교환(Context Switching)이 잦아져서 **오버헤드 증가**

<br>
<hr>

### HRN (Hightest Response-ratio Next)
```
우선순위를 계산하여 점유 불평등을 보완한 방법(SJF의 단점 보완, 기아 문제(Starvation)를 해결)

* 우선순위 = (대기시간 + 실행시간) / (실행시간)
```

<br>
<hr>

### Multilevel Queue Scheduling
```
프로세스를 여러 우선순위 큐로 분류하여 처리
```

<img src="https://images.javatpoint.com/operating-system/images/multilevel-queue-scheduling-in-operating-system.png">

#### 특징
- 우선순위가 낮은 큐들이 실행 못하는 걸 방지하고자 **각 큐마다 다른 Time Quantum**을 설정
- 우선순위 ↑ : Time Quantum ↓
- 우선순위 ↓ : Time Quantum ↑

<img src="https://user-images.githubusercontent.com/13609011/91695480-2a4e5b00-eba9-11ea-8dbf-390bf0a73c10.png">

<br>
<hr>

### Multilevel Feedback Queue Scheduling
```
Multilevel Queue와 비슷하지만, 프로세스의 우선순위를 동적으로 조정
```

<img src="https://i0.wp.com/tutorialwing.com/wp-content/uploads/2018/08/tutorialwing-os-multilevel-feedback-queue-scheduling-example.png?resize=860%2C376&ssl=1">

#### 특징
- 최상위 큐는 가장 높은 우선순위를 가지며, 최하위 큐는 가장 낮은 우선순위를 가짐
- 각 큐는 독립적인 스케줄링 알고리즘(예: Round Robin, FCFS 등)을 사용 가능
- 높은 우선순위 큐일수록 Time Quantum ↓
- 프로세스가 할당된 Time Quantum 내에 실행을 완료하지 못하면 **낮은 우선순위 큐**로 이동
- 기아 문제(Starvation)는 **에이징(Aging)**으로 해결

<br>


## CPU 스케줄링 평가 기준
### Throughput (처리량)
- 단위 시간당 완료된 프로세스 수

### Turnaround Time (소요 시간)
- 프로세스가 도착해서 완료될 때까지 걸린 시간

### Response Time (응답 시간)
- 프로세스가 요청을 제출한 후 첫 번째 응답까지 걸린 시간