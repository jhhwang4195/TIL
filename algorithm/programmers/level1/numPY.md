## 문자열 내 p와 y의 개수 Level 1  

numPY함수는 대문자와 소문자가 섞여있는 문자열 s를 매개변수로 입력받습니다.   
s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 리턴하도록 함수를 완성하세요.   
'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다.   
예를들어 s가 “pPoooyY”면 True를 리턴하고 “Pyy”라면 False를 리턴합니다.   

## template
```python
def numPY(s):

    return True


# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( numPY("pPoooyY") )
print( numPY("Pyy") )
```

## source
```python
def numPY(s):
    s = s.lower()
    if s.count("p") == s.count("y") or (s.count("p") == 0 and s.count("y") == 0):
        return True
    else:
        return False

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( numPY("pPoooyY") )
print( numPY("Pyy") )
```

## good1
한줄로 끝내는 센스..
if로 'p', 'y' 모두 하나도 없는 경우를 체크할 필요가 없음!!
```python
def numPY(s):
    # 함수를 완성하세요
    return s.lower().count('p') == s.lower().count('y')

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( numPY("pPoooyY") )
print( numPY("Pyy") )
```

## good2
```python
def numPY(s):
    # 함수를 완성하세요
    if(s.upper().count('P')==s.upper().count('Y')):
        return True
    return False


# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( numPY("pPoooyY") )
print( numPY("Pyy") )
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/97
