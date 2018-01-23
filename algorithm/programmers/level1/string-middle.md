## 가운데 글자 가져오기 Level 1

getMiddle메소드는 하나의 단어를 입력 받습니다.  
단어를 입력 받아서 가운데 글자를 반환하도록 getMiddle메소드를 만들어 보세요.  
단어의 길이가 짝수일경우 가운데 두글자를 반환하면 됩니다.  
예를들어 입력받은 단어가 power이라면 w를 반환하면 되고, 입력받은 단어가 test라면 es를 반환하면 됩니다.  

## template
```
def string_middle(str):

    return ""

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(string_middle(""))
print(string_middle("p"))
print(string_middle("power"))
print(string_middle("school"))
```

## source
```
def string_middle(str):
    middle_idx = int(len(str)/2)
    if len(str) % 2 == 0:
        return str[middle_idx-1:middle_idx+1]
    else:
        return str[middle_idx]

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(string_middle(""))
print(string_middle("p"))
print(string_middle("power"))
print(string_middle("school"))
```

## good
문자열 길이가 5이면 2부터 3까지(index 2번째 출력)  
문자열 길이가 6이면 2부터 4까지(index 2,3번째 출력)  
```
def string_middle(str):
    #print("(len(str)-1)//2=%d, len(str)//2+1=%d" % ((len(str)-1)//2, len(str)//2+1))
    return str[(len(str)-1)//2:len(str)//2+1]

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(string_middle(""))
print(string_middle("p"))
print(string_middle("power"))
print(string_middle("school"))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/82
