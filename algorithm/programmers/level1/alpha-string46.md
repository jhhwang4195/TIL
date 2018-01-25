## 문자열 다루기 기본 Level 1
alpha_string46함수는 문자열 s를 매개변수로 입력받습니다.   
s의 길이가 4혹은 6이고, 숫자로만 구성되있는지 확인해주는 함수를 완성하세요.   
예를들어 s가 “a234”이면 False를 리턴하고 “1234”라면 True를 리턴하면 됩니다   

## template
```python
def alpha_string46(s):
    #함수를 완성하세요

    return True


# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( alpha_string46("a234") )
print( alpha_string46("1234") )
```

## source
```python
import re

def alpha_string46(s):
    return bool(re.match("\d{4,6}", s)) and (len(s) == 4 or len(s) == 6)

# 아래는 테스트로 출력해 보기 위한 코드입니다.
# False
print( alpha_string46("") )
print( alpha_string46("a") )
print( alpha_string46("a234") )
print( alpha_string46("34K3") )
print( alpha_string46("KK33") )
print( alpha_string46("KKKK") )
print( alpha_string46("1") )
print( alpha_string46("12345") )
print( alpha_string46("1234567") )

# True
print( alpha_string46("1234") )
print( alpha_string46("123456") )
```

## good1
```python
def alpha_string46(s):
    return s.isdigit() and len(s) in [4, 6]
    #return s.isdigit() and (len(s) == 4 or len(s) == 6)

# 아래는 테스트로 출력해 보기 위한 코드입니다.
# False
print( alpha_string46("") )
print( alpha_string46("a") )
print( alpha_string46("a234") )
print( alpha_string46("34K3") )
print( alpha_string46("KK33") )
print( alpha_string46("KKKK") )
print( alpha_string46("1") )
print( alpha_string46("12345") )
print( alpha_string46("1234567") )

# True
print( alpha_string46("1234") )
print( alpha_string46("123456") )
```

## good2
```python
import re

def alpha_string46(s):
    return bool(re.match("^(\d{4}|\d{6})$", s))

# 아래는 테스트로 출력해 보기 위한 코드입니다.
# False
print( alpha_string46("") )
print( alpha_string46("a") )
print( alpha_string46("a234") )
print( alpha_string46("34K3") )
print( alpha_string46("KK33") )
print( alpha_string46("KKKK") )
print( alpha_string46("1") )
print( alpha_string46("12345") )
print( alpha_string46("1234567") )

# True
print( alpha_string46("1234") )
print( alpha_string46("123456") )
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/100
