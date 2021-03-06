## 피보나치 수 Level 1

피보나치 수는 F(0) = 0, F(1) = 1일 때, 2 이상의 n에 대하여 F(n) = F(n-1) + F(n-2) 가 적용되는 점화식입니다.  
2 이상의 n이 입력되었을 때, fibonacci 함수를 제작하여 n번째 피보나치 수를 반환해 주세요.  
예를 들어 n = 3이라면 2를 반환해주면 됩니다.  

## template
```python
def fibonacci(num):
    answer = 0

    return answer

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(fibonacci(3))
```

## source
```python
def fibonacci(num):
    answer = [0,1]
    
    if num == 0:
        return 0

    for i in range(2, num+1):
        answer.append(answer[i-1] + answer[i-2])
        print(answer)

    return answer[-1]

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(fibonacci(0))
print(fibonacci(1))
print(fibonacci(2))
print(fibonacci(3))
print(fibonacci(4))
print(fibonacci(5))
print(fibonacci(6))
```

## good
```python
def fibonacci(num):
    a, b = 0, 1
    for i in range(num):
        a, b = b, a+b
    return a

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(fibonacci(0))
print(fibonacci(1))
print(fibonacci(2))
print(fibonacci(3))
print(fibonacci(4))
print(fibonacci(5))
print(fibonacci(6))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/5
