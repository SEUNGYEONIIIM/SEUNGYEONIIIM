# R 강의노트2 복습

## Double ##
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

## integer ##
as.integer() 함수
```R
n<-as.integer(5) #5를 정수로 변환하여 변수 n에 저장
is.integer(n) #n이 정수인지
typeof(n) #n의 type
typeof(n+k)
```
```R
[1] TRUE #as.integer() 함수를 사용하여 double->integer 변환
[1] "integer"
[1] "double" #n+k의 type
```

## Lobical ##
```R
TR<-TRUE
typeof(TR)
```
```R
[1] "lobical" #TR의 type
```
TRUE =1 , False = 0
```R
TR+TR
```
```R
[1] 2
```

## Character ##
```R
chstr<-"name"
tyepof(chstr)
```
```R
[1] "character" #chstr의 type
```
```R
num<-as.character(5) #double인 5를 as.character함수를 이용해 character로 변환
typeof(num)
```
```R
[1] "character" #num의 type
```

## Vectors ##
R은 기본적으로 스칼라가 아닌 벡터 
```R
x<-3
is.vector(x)
x[1] 
x[2]
```
```
[1] TRUE 
[1] 3
[1] NA #결측값 Not Available (missing value)

```

## Creating Vectors ##
벡터를 만들 수 있는 함수 : c(), vector() 등

c() ; combine : 기본적으로 열 벡터로 생성됨
```R
c(1,2,3,4,5)
c(c(1,2,3),4,5)
```
```R
[1] 1 2 3 4 5
[1] 1 2 3 4 5
```
sequence
```R
2:5 
2:-1
```
```R
[1] 2 3 4 5 
[1] 2 1 0 -1
```
벡터의 모든 요소들은 같은 타입
```R
typeof(1:4)
```
```
[1] "integer" #1:4 -> double이 아닌 integer 
```
integer과 double이 같이 있는 경우->double
```R
typeof(c(1:5, 10.5)) # 1:5는 integer, 10.5는 double
```
```R
[1] "double" 
```
벡터 안에 character가 있으면 모든 요소가 "character"
```R
typeof(c(1:5, 10.5, "next")) #integer, double, character
```
```R
[1] "character"
```

## Indexing and Subsetting Vectors ##
```R
x<-c(0,1,1,2,3,5,8,13) #벡터 생성
x[2:4] #인덱싱; x의 2번째값부터 4번째값까지
```
```R
[1] 1 1 2
```
인덱싱으로 값 변경
```R
x[1]<-1;x
```
```R
[1] 1 1 1 2 3 5 8 13
```
c()함수를 이용한 인덱싱
```R
x[c(2,4,6,8)] # 2, 4, 6, 8번째 값
```
```
[1] 1 2 5 13
```
특정 원소 제외하고 출력
```R
x[-8] #8번째 원소를 제외하고 출력
```
```R
[1] 1 1 1 2 3 5 8
```
논리값으로 값 선택하기
```R
x[c(T,T,T,T,F,F,F,F)] #TRUE인 값만 출력됨
```
[1] 1 1 1 2 # TRUE인 1~4번째 값만 출력
```

## Adding and Deleting Vector Elements ##
```R
x<-c(11,12,13,15) #벡터 생성
x<-c(x[1:3], 14, x[4]) #14를 추가
```
```R
[1] 11 12 13 15
[1] 11 12 13 14 15 #x에 새로운 벡터가 저장됨
```

## Vector Operations ##
```R
x<-c(1,2,3)
y<-c(1,2,4)

x+y
x-y
x*y
x/y
x==y
x<y
x>1
x[x>1] #2,3번째 값만 출력
y[x>2]<-0;y #3번째 값을 0으로 변경
```
```R
[1] 2 4 7
[1] 0 0 -1
[1] 1 4 12
[1] 1.00 1.00 0.75
[1] TRUE TRUE FALSE
[1] FALSE FALSE TRUE
[1] FALSE TRUE TRUE
[1] 2 3
[1] 1 2 0
````

## Filtering ##
```R
x <- c(1,2,3)
y <- c(1,2,4)

x==y
x[x==y] #x의 값과 y의 값이 같은 순서의 값만 출력
x[x<y] #x의 값이 y의 값보다 작은 순서의 값만 출력
```
```R
[1] 1 2 
[1] 3
````

## Recycling(Broadcasting) ##
벡터의 길이가 다른 경우 반복
```R
x<-c(1,2,3,4,5,6,7)
y<-c(1,2)

x-y

