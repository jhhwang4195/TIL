## 약수의 합 Level 1

어떤 수를 입력받아 그 수의 약수를 모두 더한 수 sumDivisor 함수를 완성해 보세요.  
예를 들어 12가 입력된다면 12의 약수는 [1, 2, 3, 4, 6, 12]가 되고, 총 합은 28이 되므로 28을 반환해 주면 됩니다.  


## template
```python
def sumDivisor(num):
    answer = 1

    return answer

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(sumDivisor(12))
```

## source
```python
def sumDivisor(num):
    answer = 0

    for i in range(1, num+1):
        if (num%i == 0):
            answer += i
            #print("i=%d, answer=%d\n" %(i, answer))

    return answer

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(sumDivisor(0))
print(sumDivisor(1))
print(sumDivisor(2))
print(sumDivisor(3))
print(sumDivisor(4))
print(sumDivisor(6))
print(sumDivisor(12))
```

## good1
한줄로 끝내버리는 센스 멋지군요ㅎㅎ
```python
def sumDivisor(num):
    return sum([i for i in range(1, num+1) if num % i == 0])

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(sumDivisor(0))
print(sumDivisor(1))
print(sumDivisor(2))
print(sumDivisor(3))
print(sumDivisor(4))
print(sumDivisor(6))
print(sumDivisor(12))
```

## good2
한줄로 끝내버리는 센스 멋지군요ㅎㅎ
성능 향상 아름답군요ㅎㅎ
```python
def sumDivisor(num):
    # num / 2 의 수들만 검사하면 성능 약 2배 향상잼
    return num + sum([i for i in range(1, (num // 2) + 1) if num % i == 0])

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(sumDivisor(0))
print(sumDivisor(1))
print(sumDivisor(2))
print(sumDivisor(3))
print(sumDivisor(4))
print(sumDivisor(6))
print(sumDivisor(12))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/2
