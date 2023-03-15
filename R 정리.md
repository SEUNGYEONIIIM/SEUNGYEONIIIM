# R 강의노트2 복습

R은 숫자를 Double로 인식
```R
k<-5
is.double(k) #k가 double 형식인지 TRUE/FALSE 논리값 반환
typeof(k) #k의 type을 알아내는 함수
```
```R
[1] TRUE
[1] "double"
```

as.integer() 함수
```R
n<-as.integer(5) #5를 정수로 변환하여 변수 n에 저장
is.integer(n) #n이 정수인지
```
```R
[1] TRUE #as.integer() 함수를 사용하여 double->integer 변환
```
