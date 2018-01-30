## x만큼 간격이 있는 n개의 숫자 Level 1

number_generator함수는 x와 n을 입력 받습니다.  
2와 5를 입력 받으면 2부터 시작해서 2씩 증가하는 숫자를 5개 가지는 리스트를 만들어서 리턴합니다.  
[2,4,6,8,10]  

4와 3을 입력 받으면 4부터 시작해서 4씩 증가하는 숫자를 3개 가지는 리스트를 만들어서 리턴합니다.  
[4,8,12]  

이를 일반화 하면 x부터 시작해서 x씩 증가하는 숫자를 n개 가지는 리스트를 리턴하도록 함수 number_generator를 완성하면 됩니다.  


## template
```python
def number_generator(x, n):
    # 함수를 완성하세요
    return []

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(number_generator(3,5))
```

## source
```python
def number_generator(x, n):
    result = []

    for idx in range(1, n+1):
        result.append(x*idx)
    return result

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(number_generator(2,5))
print(number_generator(3,4))
```

## good
```python
def number_generator(x, n):
    # 함수를 완성하세요
    return [i * x + x for i in range(n)]

print(number_generator(2, 5))
print(number_generator(3, 4))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/135
