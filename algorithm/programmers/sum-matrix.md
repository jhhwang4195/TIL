## ¿¿¿ ¿¿ Level 1
¿¿¿ ¿¿¿ ¿¿ ¿¿ ¿¿¿ ¿¿ ¿ ¿¿¿ ¿¿ ¿, ¿¿ ¿¿ ¿¿ ¿¿ ¿¿ ¿¿¿ ¿¿¿.
2¿¿ ¿¿¿ ¿¿¿¿ sumMatrix ¿¿¿ ¿¿¿¿ ¿¿ ¿¿¿ ¿¿¿ ¿¿¿ ¿¿¿.

¿¿ ¿¿ 2x2 ¿¿¿ A = ((1, 2), (2, 3)), B = ((3, 4), (5, 6)) ¿ ¿¿¿¿,
¿¿ 2x2 ¿¿¿ ((4, 6), (7, 9))¿ ¿¿¿¿ ¿¿¿.
(¿¿¿ ¿¿¿¿ ¿¿¿¿ ¿¿¿ ¿¿¿¿¿¿.)


## template
```
def sumMatrix(A,B):
    answer = []
    
    return answer

# ¿¿¿ ¿¿¿¿ ¿¿¿ ¿¿ ¿¿ ¿¿¿¿¿.
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
```

## source
```
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

# # ¿¿¿ ¿¿¿¿ ¿¿¿ ¿¿ ¿¿ ¿¿¿¿¿.
# 2*2 matrix
print(sumMatrix([[1,2], [2,3]], [[3,4],[5,6]]))
print(sumMatrix([[1,2], [3,4]], [[1,2],[3,4]]))
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[3,4]]))
print(sumMatrix([[-1,-2], [-3,-4]], [[1,2],[5,5]]))

# 3*3 matrix
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [1,2,3]]))
print(sumMatrix([[1,2,3], [1,2,3], [1,2,3]], [[1,2,3], [1,2,3], [-1,-2,-3]]))

# 2*1 matrix
print(sumMatrix([[1,2], [2,3]], [[3,4]]))
```

## good1
zip¿ ¿¿¿¿ ¿¿¿¿¿¿..
2*1 matrix¿ ¿¿¿ ¿¿ ¿¿¿¿..
```
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
numpy¿ ¿¿¿¿ ¿¿¿¿ ¿¿¿..
2*1 matrix¿ ¿¿¿ ¿¿ ¿¿¿¿..
```
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
