git 명령으로 undo 하는 방법을 정리한다.

## 1. add 전에 undo 하기
```
$ git checkout -- hello.c
```
## 2. add 후에 undo 하기
```
$ git reset HEAD hello.c
$ git checkout -- hello.c
```

## 3. commit 후에 undo 하기
```
$ git reset --hard HEAD~1
```

## 4. push 후에 undo 하기
```
$ git reset --hard HEAD~1
$ git push -f origin master
```
