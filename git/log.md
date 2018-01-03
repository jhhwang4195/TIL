git log를 사용하는 다양한 방법을 정리합니다.


## 2주 전부터 현재까지의 변경사항 보기
```
git log --no-merges --raw --since='2 weeks ago'
git whatchanged --since='2 weeks ago'
```

## --before, --after 옵션을 사용한 commit 날짜 필터링
```
git log --before 2017-12-10
git log --after 2017-12-10
```

## --before, --after 옵션을 사용한 commit 날짜 범위 지정 후 필터링
```
git log --after 2017-12-10 --before 2017-12-12
```

## author 정보로 commit 정보를 필터링
```
git log --author=jhhwang
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

## commit에 대한 모든 변경 사항 확인
참고로 -p 옵션은 각 커밋의 diff 결과를 출력해준다.
```
git log -p
git log -p --raw
```

## 파일 하나에 대한 변경 이력 확인하기
```
git log <filename>
git log -p <filename>
```

## commit별로 변경된 내용 요약 (추가 된 행 수, 제거 된 행 수) 확인
```
git log --stat
```

## commit에 대한 정보를 한줄로 표시하기
```
git log --oneline
git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

## author, title에 대한 그룹을 지어 commit 정보를 표시
```
git shortlog
```

## author별로 commit을 몇번했는지 확인
```
git shortlog -se
```

## author별로 작성한 소스 코드의 라인 수 확인
```
git log --author="_Your_Name_Here_" --pretty=tformat: --numstat \
| gawk '{ add += $1; subs += $2; loc += $1 - $2 } END { printf "added lines: %s removed lines: %s total lines: %s\n", add, subs, loc }' -

git log --shortstat --pretty="%cE" | sed 's/\(.*\)@.*/\1/' | grep -v "^$" | awk 'BEGIN { line=""; } !/^ / { if (line=="" || !match(line, $0)) {line = $0 "," line }} /^ / { print line " # " $0; line=""}' | sort | sed -E 's/# //;s/ files? changed,//;s/([0-9]+) ([0-9]+ deletion)/\1 0 insertions\(+\), \2/;s/\(\+\)$/\(\+\), 0 deletions\(-\)/;s/insertions?\(\+\), //;s/ deletions?\(-\)//' | awk 'BEGIN {name=""; files=0; insertions=0; deletions=0;} {if ($1 != name && name != "") { print name ": " files " files changed, " insertions " insertions(+), " deletions " deletions(-), " insertions-deletions " net"; files=0; insertions=0; deletions=0; name=$1; } name=$1; files+=$2; insertions+=$3; deletions+=$4} END {print name ": " files " files changed, " insertions " insertions(+), " deletions " deletions(-), " insertions-deletions " net";}'
```

## Reference
* https://github.com/git-tips/tips
* https://www.thegeekstuff.com/2014/04/git-log/
* https://devhints.io/git-log
* https://git-scm.com/book/ko/v1/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0
* https://stackoverflow.com/questions/1265040/how-to-count-total-lines-changed-by-a-specific-author-in-a-git-repository
