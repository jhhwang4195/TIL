git blame 명령으로 그 메소드의 각 줄을 누가 언제 마지막으로 고쳤는지 찾아낼 수 있다.

어떤 소스에 문제가 있을 때 누가 범인인지 찾아보자.

## 1. 특정 파일의 라인별 코드 작성자 찾기
```
$ git blame main.py
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900  1) #!/usr/bin/python
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900  2) 
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900  3) def get_hwang():
1bfc577b (telcosn  2017-12-05 12:45:49 +0900  4)     return 'hwang'
1bfc577b (telcosn  2017-12-05 12:45:49 +0900  5) 
1bfc577b (telcosn  2017-12-05 12:45:49 +0900  6) def get_telco():
1bfc577b (telcosn  2017-12-05 12:45:49 +0900  7)     return 'telco'
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900  8) 
f54a451f (hwauni   2017-12-05 14:59:38 +0900  9) def get_lee():
f54a451f (hwauni   2017-12-05 14:59:38 +0900 10)     return 'lee'
f54a451f (hwauni   2017-12-05 14:59:38 +0900 11) 
d1e373c6 (terriyou 2017-12-11 10:59:05 +0900 12) def get_terriyou():
d1e373c6 (terriyou 2017-12-11 10:59:05 +0900 13)     return 'terriyou'
d1e373c6 (terriyou 2017-12-11 10:59:05 +0900 14) 
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900 15) if __name__ == "__main__": 
1bfc577b (telcosn  2017-12-05 12:45:49 +0900 16)     print ("%s" % get_hwang())
1bfc577b (telcosn  2017-12-05 12:45:49 +0900 17)     print ("%s" % get_telco())
f54a451f (hwauni   2017-12-05 14:59:38 +0900 18)     print ("%s" % get_lee())
d1e373c6 (terriyou 2017-12-11 10:59:05 +0900 19)     print ("%s" % get_terriyou())
```

## 2. 특정 파일의 특정 라인 코드 작성자 찾기
-L 옵션에서 시작 라인과 끝 라인을 설정한다.
```
$ git blame -L 15,19 main.py
^3959a78 (jhhwang  2017-12-05 12:35:08 +0900 15) if __name__ == "__main__": 
1bfc577b (telcosn  2017-12-05 12:45:49 +0900 16)     print ("%s" % get_hwang())
1bfc577b (telcosn  2017-12-05 12:45:49 +0900 17)     print ("%s" % get_telco())
f54a451f (hwauni   2017-12-05 14:59:38 +0900 18)     print ("%s" % get_lee())
d1e373c6 (terriyou 2017-12-11 10:59:05 +0900 19)     print ("%s" % get_terriyou())
```

## 3. 특정 파일의 특정 라인 코드 작성자 메일 주소 출력
```
$ git blame -L 15,19 main.py -e
^3959a78 (<jhhwang@telcoware.com> 2017-12-05 12:35:08 +0900 15) if __name__ == "__main__": 
1bfc577b (<telcosn@naver.com>     2017-12-05 12:45:49 +0900 16)     print ("%s" % get_hwang())
1bfc577b (<telcosn@naver.com>     2017-12-05 12:45:49 +0900 17)     print ("%s" % get_telco())
f54a451f (<hwauni@telcoware.com>  2017-12-05 14:59:38 +0900 18)     print ("%s" % get_lee())
d1e373c6 (<terriyou@naver.com>    2017-12-11 10:59:05 +0900 19)     print ("%s" % get_terriyou())
```
