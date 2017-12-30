# commit message를 multi line으로 작성하기
commit message를 여러줄로 작성하는 방법을 정리한다.
상황에 따라 적절한 방법을 사용하면 될거 같다.
자세한 내용을 하단의 Reference를 참고하면 된다.

## 방법1) git commit
vim에서 commit 메시지를 자유롭게 작성할수 있다.

## 방법2) git comit -m 옵션 사용
```
$ git commit -m "this is
> a line
> with new lines
> maybe"
```
```
$ git log -1
commit 3ca8ead106c165d26a3ccdc72cb3847b6f82a80d
Author: jhhwang <jhhwang4195@gmail.com>
Date:   Fri Dec 29 10:54:35 2017 +0900

this is
> a line
> with new lines
> maybe
```

## 방법3) git commit에서 -m 옵션을 여러번 사용
```
$ git commit -m "My head line" -m "My content line."
```
```
$ git log -1
commit 9491e62d7e542db2b2afd18e50b5bda3c363b1ad
Author: jhhwang <jhhwang4195@gmail.com>
Date:   Fri Dec 29 10:57:02 2017 +0900

My head line

My content line.
```

## 방법4) git commit에서 $'string' 사용
```
$ git commit -m $'first line\nsecond line'
```
```
$ git log -1
commit 464aeb3396cc49ca8c1f243921882b0d96e3214d
Author: jhhwang <jhhwang4195@gmail.com>
Date:   Fri Dec 29 11:02:26 2017 +0900

first line
second line
```

## 방법5) git commit에서 $'string' 사용
```
$ git commit -m "$(echo -e "test\ntest")"
```

```
$ git log -1
commit 30db55403038d3b54b9ce32dcb6394c5a7805890
Author: jhhwang <jhhwang4195@gmail.com>
Date:   Fri Dec 29 11:03:54 2017 +0900

test
test
```
