## 수박수박수박수박수박수? Level 1
water_melon함수는 정수 n을 매개변수로 입력받습니다.  
길이가 n이고, 수박수박수...와 같은 패턴을 유지하는 문자열을 리턴하도록 함수를 완성하세요.  
예를들어 n이 4이면 '수박수박'을 리턴하고 3이라면 '수박수'를 리턴하면 됩니다.  

## template
```python
def water_melon(n):
    # 함수를 완성하세요.
    return ""

# 실행을 위한 테스트코드입니다.
print("n이 3인 경우: " + water_melon(3));
print("n이 4인 경우: " + water_melon(4));
```

## source
```python
def water_melon(n):
    # 함수를 완성하세요.
    result = ""

    for i in range (0, n):
        if i % 2 == 0:
            result += "수"
        else:
            result += "박"
    
    return result


# 실행을 위한 테스트코드입니다.
print("n이 3인 경우: " + water_melon(3));
print("n이 4인 경우: " + water_melon(4));
```

## good1
```python
def water_melon(n):
    s = "수박" * n
    return s[:n]


# 실행을 위한 테스트코드입니다.
print("n이 3인 경우: " + water_melon(3));
print("n이 4인 경우: " + water_melon(4));
```

## good2
```python
def water_melon(n):
    return "수박"*(n//2)+"수"*(n%2)

# 실행을 위한 테스트코드입니다.
print("n이 3인 경우: " + water_melon(3));
print("n이 4인 경우: " + water_melon(4));
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/102
