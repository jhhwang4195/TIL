백그라운드로 스크립트를 실행하는 방법에 대해 정리한다.


## &를 사용하여 백그라운드 작업
터미널 세션(telent, ssh)을 끊으면 백그라운드 작업도 종료된다.
```
$ test.sh &
```

## nohup을 사용하여 백그라운드 작업
터미널 세션(telent, ssh)을 끊으면 백그라운드 작업은 종료되지 않는다.
nohup으로 실행된 쉘 스크립트는 자동으로 nohup.out이라는 이름으로 nohup을 실행한 위치에 자동으로 생성된다.
```
$ nohup test.sh &
```

## nohup.out 파일 저장하지 않기
```
$ nohup test.sh 1>/dev/null 2>&1 &
```

## 백그라운드 작업 종료
```
$ ps -aef | grep test.sh
$ pkill [pid of test.sh]
```

## Reference
* http://brownbears.tistory.com/164
* http://jjinisystem.tistory.com/12
* http://changpd.blogspot.kr/2013/04/linux-nohup-xxxsh.html
* https://serverfault.com/questions/402496/what-is-does-the-ampersand-symbol-mean-with-nohup
