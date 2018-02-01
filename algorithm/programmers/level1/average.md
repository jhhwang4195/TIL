## 평균구하기 Level 1

함수를 완성해서 매개변수 array의 평균값을 return하도록 만들어 보세요.   
어떠한 크기의 array가 와도 평균값을 구할 수 있어야 합니다.   

## template
```python
def average(array):
    # 함수를 완성해서 매개변수 array의 평균값을 return하도록 만들어 보세요.
    return 0

# 아래는 테스트로 출력해 보기 위한 코드입니다.
list = [5,3,4] 
print("평균값 : {}".format(average(array)));
```

## source
```python
def average(array):
    # 함수를 완성해서 매개변수 array의 평균값을 return하도록 만들어 보세요.
    
    return sum(array)/len(array)*1.0

# 아래는 테스트로 출력해 보기 위한 코드입니다.
#list = [5,3,4] 
list = [5,3,5] 
print("평균값 : {}".format(average(list)));

```

## good
```python
def average(array):
    # 함수를 완성해서 매개변수 array의 평균값을 return하도록 만들어 보세요.
    if len(array) == 0:
        return 0;

    return sum(array)/len(array)*1.0

# 아래는 테스트로 출력해 보기 위한 코드입니다.
#list = [5,3,4]
#list = [5,3,5]
list = []
print("평균값 : {}".format(average(list)));
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/128
