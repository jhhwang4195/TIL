# 자주 사용하는 git config 설정


## git config 명령을 이용한 설정
```
git config --global user.name "jhhwang"
git config --global user.email jhhwang4195@gmail.com

git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

git config --global color.branch auto
git config --global color.diff auto
git config --global color.status auto

git config --global color.branch.current "yellow reverse"
git config --global color.branch.local "yellow"
git config --global color.branch.remote "green"

git config --global color.diff.meta "yellow bold"
git config --global color.diff.frag "magenta bold"
git config --global color.diff.old "red bold"
git config --global color.diff.new "green bold"

git config --global color.status.added "yellow"
git config --global color.status.changed "green"
git config --global color.status.untracked "cyan"

git config --global merge.tool vimdiff
```

## .gitconfig 파일 직접 수정
* vi ~/.gitconfig 
```
[user]
	name = jhhwang
	email = jhhwang4195@gmail.com

[alias]
	lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
	st = status

[color]
	branch = auto
	diff = auto
	status = auto

[color "branch"]
	current = yellow reverse
	local = yellow
	remote = green

[color "diff"]
	meta = yellow bold
	frag = magenta bold
	old = red bold
	new = green bold

[color "status"]
	added = yellow
	changed = green
	untracked = cyan

[merge]
	tool = vimdiff
```

## Reference
* https://www.leaseweb.com/labs/2013/08/git-tip-beautiful-colored-and-readable-output/
* https://gist.github.com/pksunkara/988716/forks
* https://git-scm.com/docs/git-config
