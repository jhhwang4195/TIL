## 제일 작은 수 제거하기 Level 1
```
rm_small함수는 list타입 변수 mylist을 매개변수로 입력받습니다.
mylist 에서 가장 작은 수를 제거한 리스트를 리턴하고, mylist의 원소가 1개 이하인 경우는 []를 리턴하는 함수를 완성하세요.
예를들어 mylist가 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10, 8, 22]면 [10, 22]를 리턴 합니다.
```

## template
```
def rm_small(mylist):

    return ''


## 아래는 테스트로 출력해 보기 위한 코드입니다.
my_list = [4, 3, 2, 1]
print("결과 {} ".format(rm_small(my_list)))
```

## source1
문제 대충 풀고나서 정답이라고 넘어갔다.
근데 다른 분들의 리뷰를 보니 실패 케이스가 있어서 오답이다.
1) mylist = []인 경우
2) mylist에 중복된 최소 값이 존재하는 경우
```
# -*- coding: utf-8 -*-
#!/usr/bin/python

def rm_small(mylist):
    mylist.remove(min(mylist))
        return mylist
```

```
# fail
my_list = []
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [0]
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [4, 3, 2, 1]
print("결과 {} ".format(rm_small(my_list)))

# fail
my_list = [4, 3, 2, 1, 1, 1]
print("결과 {} ".format(rm_small(my_list)))
```

## source2
실패케이스에 대한 로직을 추가해서 보완했지만 별로 좋은 소스는 아니다.
```
# -*- coding: utf-8 -*-
#!/usr/bin/python

def rm_small(mylist):
    if mylist == []:
        return mylist

    min_val = min(my_list)
    for i in mylist:
        try:
            mylist.remove(min_val)
        except Exception as err:
            break

    return mylist
```

```
# success
my_list = []
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [0]
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [4, 3, 2, 1]
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [4, 3, 2, 1, 1, 1]
print("결과 {} ".format(rm_small(my_list)))
```

## good
어떤 멋진 분은 이렇게 한줄로 명확하고 깔끔하게 하셨다.
감동적인 소스다ㅎㅎ
```
# -*- coding: utf-8 -*-
#!/usr/bin/python

def rm_small(mylist):
    return [i for i in mylist if i > min(mylist)]
        return mylist
```

```
# success
my_list = []
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [0]
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [4, 3, 2, 1]
print("결과 {} ".format(rm_small(my_list)))

# success
my_list = [4, 3, 2, 1, 1, 1]
print("결과 {} ".format(rm_small(my_list)))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/121
