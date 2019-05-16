# kill
프로세스에게 신호를 보낼 수 있는 명령어

## 사용법

```
kill [-s signal_name] pid...
kill -l [exit_status]
kill -signal_name pid...
kill -signal_number pid...
```

* `-l` : `exit_status` 를 생략하면 상태 리스트를 출력하고, 상태를 입력하면 해당 상태의 `signal_number` 출력
* `-s` : 프로세스에게 입력한 `signal_name` 신호 전송

| signal number | signal name | 설명 |
|---------------|-------------|------|
| 1             | HUP (hang up)   | 터미널과 시스템의 연결이 끊어지면 터미널의 프로세스에게 보내는 신호 |
| 2             | INT (interrupt) | 인터럽트 신호 |
| 3             | QUIT (quit)     | quit 신호 |
| 6             | ABRT (abort)    | 시스템이 비정상적으로 종료되면 관련 정보를 남기는 신호 |
| 9             | KILL            | 프로세스를 종료시키는 신호 (즉시 종료)  |
| 14            | ALRM            | 특정 시간 후, 신호 발생 |
| 15            | TERM (software termination signal) | 프로세스를 종료시키는 신호 (종료 프로세스가 있다면 실행) |


``` shell
# pid가 10, 15 프로세스 종료
$ kill 10 15

# TERM 신호로 pid가 10인 프로세스 종료
$ kill -15 10
$ kill -s TERM 10
```
