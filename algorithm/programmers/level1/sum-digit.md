## 자릿수더하기 Level 1

sum_digit함수는 자연수를 전달 받아서 숫자의 각 자릿수의 합을 구해서 return합니다.  
예를들어 number = 123이면 1 + 2 + 3 = 6을 return하면 됩니다.  
sum_digit함수를 완성해보세요.   

## template
```python
def sum_digit(number):
    '''number의 각 자릿수를 더해서 return하세요'''

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : {}".format(sum_digit(123)));
```

## source
```python
def sum_digit(number):
    sum = 0

    for i in str(number):
        sum += int(i)

    return sum

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : {}".format(sum_digit(123)));
```

## good1
재귀 함수를 사용함
```python
def sum_digit(number):
    if number < 10:
        return number;
    return (number % 10) + sum_digit(number // 10)

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : {}".format(sum_digit(123)));
```

## good2
map(f, iterable)은 각 요소가 함수 f에 의해 수행된 결과를 묶어서 리턴하는 함수,  
str(number)각 인덱스에 int()함수를 수행해서 변환 후 sum()  
```python
def sum_digit(number):
    return sum(map(int,str(number)))

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : {}".format(sum_digit(123)));
```

## good3
정수 리스트에 sum을 이용해서 합 구하기
```python
def sum_digit(number):
    return sum([int(i) for i in str(number)])

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : {}".format(sum_digit(123)));
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/116
