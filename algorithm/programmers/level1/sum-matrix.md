## 행렬의 덧셈 Level 1
행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다.<br>
2개의 행렬을 입력받는 sumMatrix 함수를 완성하여 행렬 덧셈의 결과를 반환해 주세요.<br>

예를 들어 2x2 행렬인 A = ((1, 2), (2, 3)), B = ((3, 4), (5, 6)) 가 주어지면,
같은 2x2 행렬인 ((4, 6), (7, 9))를 반환하면 됩니다.<br>
(어떠한 행렬에도 대응하는 함수를 완성해주세요.)<br>


## template
```python
def sumMatrix(A,B):
    answer = []
    
    return answer

# 아래는 테스트로 출력해 보기 위한 코드입니다.
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
```

## source
```python
def sumMatrix(A,B):
    answer = []

    if len(A) != len(B):
         return answer
        
    for i in range(len(A)):
        tmp = []
        for j in range(len(A[i])):
            tmp.append(A[i][j] + B[i][j])
        answer.append(tmp)

    return answer

# 아래는 테스트로 출력해 보기 위한 코드입니다.
# 2*2 matrix
# success
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
# success
print(sumMatrix([[1,2], [3,4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[5,5]]))

# 3*3 matrix
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [1,2,3]]))
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [-1,-2,-3]]))

# 2*1 matrix
# success
print(sumMatrix([[1,2], [2,3]], [[3,4]]))
```

## good1
zip은 생소한데 찾아봐야겠군..<br>
2*1 matrix는 결과가 조금 이상하군..<br>
```python
def sumMatrix(A,B):
    answer = [[c + d for c, d in zip(a, b)] for a, b in zip(A,B)]
    return answer

# 2*2 matrix
# success
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
# success
print(sumMatrix([[1,2], [3,4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[5,5]]))

# 3*3 matrix
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [1,2,3]]))
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [-1,-2,-3]]))

# 2*1 matrix
# ??
print(sumMatrix([[1,2], [2,3]], [[3,4]]))
```

## good2
numpy를 써서하면 이렇게도 되는군..<br>
2*1 matrix는 결과가 조금 이상하군..<br>
```python
import numpy as np
def sumMatrix(A,B):
    A=np.array(A)
    B=np.array(B)
    answer=A+B
    return answer.tolist()

# 2*2 matrix
# success
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
# success
print(sumMatrix([[1,2], [3,4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[3,4]]))
# success
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[5,5]]))

# 3*3 matrix
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [1,2,3]]))
# success
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [-1,-2,-3]]))

# 2*1 matrix
# ??
print(sumMatrix([[1,2], [2,3]], [[3,4]]))
```

## Reference
* https://programmers.co.kr/learn/challenge_codes/8
* https://wayhome25.github.io/algorithm/2017/02/26/SumMatrix/
