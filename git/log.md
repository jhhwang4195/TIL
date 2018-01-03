git log를 사용하는 다양한 방법을 정리합니다.


## 2주 전부터 현재까지의 변경사항 보기
```
git log --no-merges --raw --since='2 weeks ago'
git whatchanged --since='2 weeks ago'
```

## 마지막 n개의 커밋 나열하기
```
git log -<n>
git log -n <n>
```

## 특정 날짜 구간 사이의 커밋 로그 출력하기
```
git log --since='JAN 1 2018' --until='JAN 3 2018'
```

## first commit 날짜 확인
```
$ git log --reverse
```
