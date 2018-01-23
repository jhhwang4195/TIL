## 짝수와 홀수 Level 1

evenOrOdd 메소드는 int형 num을 매개변수로 받습니다.  
num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하도록 evenOrOdd에 코드를 작성해 보세요.  
num은 0이상의 정수이며, num이 음수인 경우는 없습니다.  

## template
```
def evenOrOdd(num):
    s = ""
    #함수를 완성하세요

    return s

#아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : " + evenOrOdd(3))
print("결과 : " + evenOrOdd(2))
```

## source
```
def evenOrOdd(num):
    if int(num) % 2:
        return "Odd"
    else:
        return "Even"

#아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : " + evenOrOdd(3))
print("결과 : " + evenOrOdd(2))

```

## good
대단하다. 아래 print 결과를 확인하면 이해가 될듯
print('1 and "Odd": %s' % (1 and "Odd"))    # Odd
print('0 and "Odd": %s' % (0 and "Odd"))    # 0
print('1 and "Odd" or "Even": %s' %(1 and "Odd" or "Even"))     # Odd
print('0 and "Odd" or "Even": %s' %(0 and "Odd" or "Even"))     # Even

```
def evenOrOdd(num):
    if int(num) % 2:
        return "Odd"
    else:
        return "Even"

#아래는 테스트로 출력해 보기 위한 코드입니다.
print("결과 : " + evenOrOdd(3))
print("결과 : " + evenOrOdd(2))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/124
