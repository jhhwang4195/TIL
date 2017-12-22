# 생성된 repository(TIL)에 처음 commit 하는 방법


## git config 설정 :+1:

* git config --global.user.name jhhwang
* git config --global user.email jhhwang4195@gmail.com

## first commit :+1:
* cd TIL
* echo "# TIL" >> README.md
* git init
* git add README.md
* git commit -m "first commit"
* git remote add origin https://github.com/jhhwang4195/TIL.git
* git push -u origin master
