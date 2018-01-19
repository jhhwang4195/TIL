구글링해서 어떤 소스 코드를 찾아서 vi에 복사하는 경우가 있다.   
그런데 auto indentation이 적용되어 아래와 같이 indendation이 이상해진다.   
아래와 같은 파이썬 코드를 작성으로 indentation 맞추기 삽질 시작..   
소스가 몇줄 안되도 겁나 짜증 폭발하겠음!!!    

## 예시
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
```

내가 원하던 것은 소스를 복사하는 경우, auto indentation을 해지하는 것이다.   
아래처럼 원본 indentation과 동일한 것을 원했다.   

## 예시
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
```

구글링 검색 키워드는 "vimrc paste auto indentation off"  
역시 stackoverflow에서 원하던 답변을 찾았다.  
상세한 정보는 하단의 Reference를 참고하세요.  

## 코드를 붙여 넣을 때 autoindent 끄기
```
:set paste
```

## autoindent 켜기
```
:set nopaste
```

위와 같이 하면 너무나 귀찮고 짜증이 폭발하겠지요?  
그래서 vimrc 파일에 아래와 같이 적용해서 F3으로 토글해서 쓰면 된다고 합니다.  

## autoindent 기능 스위칭 하기
```
set pastetoggle=<F3>
```

실제로 해보니까 정말 잘되네요.  
야호!!! 삽질을 줄일수 있겠다ㅎㅎ  

## Refererce
* https://stackoverflow.com/questions/2514445/turning-off-auto-indent-when-pasting-text-into-vim
