## 문제
```
두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환해주는 gcdlcm 함수를 완성해 보세요. 
배열의 맨 앞에 최대공약수, 그 다음 최소공배수를 넣어 반환하면 됩니다. 
예를 들어 gcdlcm(3,12) 가 입력되면, [3, 12]를 반환해주면 됩니다.
```

## template
```
def gcdlcm(a, b):

    return answer

print(gcdlcm(3,12))
```

## source
```
def gcdlcm(a, b):
    answer = []

    gcd = lcm = 0

    min_val = min(a, b)
    for val in range(1, min_val+1):
        if (a % val == 0) and (b % val == 0):
            gcd = val

    lcm = int(a*b/gcd)
    answer = [gcd, lcm]

    return answer

print(gcdlcm(3,12))
```

## good
```
def gcdlcm(a, b):
    c, d = max(a, b), min(a, b)
    t = 1
    while t > 0:
        t = c % d
        c, d = d, t
    answer = [c, int(a*b/c)]

    return answer

print(gcdlcm(3,12))
```

```
def gcdlcm(a, b):
    for i in range(a):
        if a%(a-i)+b%(a-i) == 0:
            return [a-i, a*b/(a-i)]

print(gcdlcm(3,12))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/11
