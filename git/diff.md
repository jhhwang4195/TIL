git diff 명령어를 정리했습니다.

## diff를 이용한 commit_id1과 commit_id2 사이의 변경사항 비교
```
git diff <commit_id1> <commit_id2>
```

## difftool을 사용한 commit_id1과 commit_id2 사이의 변경사항 비교
git difftool [-t <tool>] <commit1> <commit2> <path>
```
git difftool -t vimdiff <commit_id1> <commit_id2>
```
