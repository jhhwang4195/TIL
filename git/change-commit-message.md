commit하고 push를 했는데 commit message가 잘못된것을 확인했다.

이때 commit message를 수정하려면 아래와 같이 한다.

## commit 메시지 수정
```
git commit --amend -m "your new message"
```

## git log 확인
```
git log -1
```

## git push
git push 하면 에러가 발생한다.
-f 옵션줘서 강제로 push하면 된다.
```
git push -f
```

## Reference
* https://help.github.com/articles/changing-a-commit-message/
* https://gist.github.com/nepsilon/156387acf9e1e72d48fa35c4fabef0b4
* https://stackoverflow.com/questions/179123/how-to-modify-existing-unpushed-commits
