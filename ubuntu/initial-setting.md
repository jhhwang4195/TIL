# 우분투 초기 설정

우분투에서 개발할 때 초기 설정할 것을 정리했습니다.

## hostname 변경
```
$ cat /etc/hostname 
$ hostname xos
```

## root 패스워드 변경
```
$ sudo passwd root 
```

## 패키지 설치
```
$ apt update -y
$ apt install -y vim htop iftop tree openssh-server lrzsz openvswitch-switch ssh
```

## ssh root 접속 설정
/etc/ssh/sshd_config 파일에서 Root Login Permit 설정한다.
```
$ PermitRootLogin yes 
```

## sshd 재기동
```
$ service sshd restart
```


## vimrc 편집
/root/.vimrc 파일을 편집한다.
```
color koehler

set tabstop=4
set softtabstop=4
set shiftwidth=4

set autoindent
set cindent
set smartindent
set noexpandtab
```
