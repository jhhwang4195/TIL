## 같은 숫자는 싫어 Level 1

no_continuous함수는 스트링 s를 매개변수로 입력받습니다.  
s의 글자들의 순서를 유지하면서, 글자들 중 연속적으로 나타나는 아이템은 제거된 배열(파이썬은 list)을 리턴하도록 함수를 완성하세요.  
예를들어 다음과 같이 동작하면 됩니다.  
* s가 '133303'이라면 ['1', '3', '0', '3']를 리턴  
* s가 '47330'이라면 [4, 7, 3, 0]을 리턴  

## template
```python
def no_continuous(s):
    # 함수를 완성하세요
    return []

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( no_continuous( "133303" ))
```

## source
```python
def no_continuous(s):
    result = []
    old_value = ""

    for value in s:
        if old_value != value:
            result.append(value)
        old_value = value

    return result

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( no_continuous( "133303" ))
print( no_continuous( "111222333" ))
print( no_continuous( "11223311" ))
```

## good1
a의 마지막 index 값과 비교해서 없으면 리스트에 추가하기
```python
def no_continuous(s):
    a = []
    for i in s:
        if a[-1:] == [i]: continue
        a.append(i)
    return a

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( no_continuous( "133303" ))
print( no_continuous( "111222333" ))
print( no_continuous( "11223311" ))
```

## good2
```python
def no_continuous(s):
    return [s[i] for i in range(len(s)) if s[i] != s[i+1:i+2]]

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print( no_continuous( "133303" ))
print( no_continuous( "111222333" ))
print( no_continuous( "11223311" ))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/86
