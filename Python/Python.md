# 파이썬 기초

### 20230117

## 0. 코드스타일 가이드
- 코드를 '어떻게 작성할지'에 대한 가이드라인
- 파이썬에서 제안하는 스타일 가이드(강의에서 사용)
  - PEP8 ()
- 각 회사/프로젝트마다 따로 스타일 가이드를 설정하기도 함
  - Google Style guide 등

![스타일가이드예시](../image/20230117/20230117_1.PNG)

### 들여쓰기
- Space Sensitive
- 문장을 구분할 때, 중괄호 대신 들여쓰기를 사용
- 들여쓰기를 할 때는 4칸 혹은 1탭을 입력
- **주의! 한 코드 안에서는 반드시 한 종류의 들여쓰기를 사용** → 혼용 금지
- Tab으로 들여쓰면 계속 탭으로 들여써야 함
- 원칙적으로는 공백 사용을 권장


## 1. 제어문

### 제어문(Control Statement)
- 순차, 선택, 반복
- 파이썬은 기본적으로 위에서부터 아래로 차례대로 명령을 수행
- **특정 상황**에 따라 코드를 선택적으로 실행(분기/조건) 하거나 계속하여 실행(반복)하는 제어가 필요함
- 제어문도 순서도(Flowchart)로 표현이 가능


## 2. 조건문

### 조건문 기본
- 조건문은 참/거짓을 판단할 수 있는 조건식과 함께 사용
  
![조건문1](../image/20230117/20230117_2.PNG)

- 조건에는 참/거짓에 대한 조건식
- 조건이 참인 경우 이후 들여쓰기 되어있는 코드블록을 실행
- 이외의 경우 else 이후 들여쓰기 되어있는 코드 블록을 실행
  - else는 선택적으로 활용할 수 있음
  
![조건문2](../image/20230117/20230117_3.PNG)

- 조건문 예시
  
![조건문 예시](../image/20230117/20230117_4.PNG)

~~~python
a = 5
if a > 5:
    print('5 초과')

else:
    print('5 이하')
print(a)
~~~

#### 조건문 실습 문제
- 조건문을 통해 변수 num의 값의 홀수/짝수 여부를 출력하시오.
  - 이때 num은 input을 통해 사용자로부터 입력을 받으시오.

~~~python
num = int(input('숫자 입력: '))
if num % 2: # == 0 등 의 값을 안넣어줘도, 0은 False의 값이 적용됨 / 반대로 0이 아닌 모든 값은 True로 적용.
    print('홀수입니다')
else:
    print('짝수입니다')
~~~

### 복수 조건문
- 복수의 조건식을 활용할 경우 elif(else if)를 활용하여 표현함.

![복수 조건문](../image/20230117/20230117_5.PNG)
- 복수조건문에서 if가 False라면 그 다음 elif로 넘어가는 구조 → ... 마지막 else까지 오는 구조.
- 중간에 True가 있다면 해당 조건문 실행한 후 빠져나감.

#### 복수조건문 실습 문제
- 미세먼지 농도에 따른 위험 등급이 다음과 같을 때, dust 값에 따라 등급을 출력하는 조건식을 작성하시오.(조건식 완료 후 미세먼지 확인 완료라는 문구 출력)
~~~python
dust = 80
if dust > 150:
    print('매우나쁨')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
else:
    print('좋음')

print('미세먼지 확인 완료!')
~~~

![복수 조건문2](../image/20230117/20230117_6.PNG)

### 중첩 조건문
- 조건문은 다른 조건문에 중첩되어 사용될 수 있음.
  - 들여쓰기에 유의하여 작성할 것.

![중첩 조건문](../image/20230117/20230117_7.PNG)

#### 복수조건문 실습 문제
- 아래의 코드에서 중첩 조건문을 활용하여 미세먼지 농도가 300이 넘는 경우 '실외 활동을 자제하세요'를 추가로 출력하고 음수인 경우 '값이 잘못되었습니다'를 출력하시오.
~~~python
dust = 500
if dust > 150:
    print('매우나쁨')
    if dust > 300:
        print('실외 활동을 자제하세요.')
elif dust > 80:
    print('나쁨')
elif dust > 30:
    print('보통')
elif dust >= 0:
    print('좋음')
else:
    print('값이 잘못 되어있습니다.')
~~~

### 조건 표현식
- 조건 표현식(Conditional Expression)이란?
- 조건 표현식을 일반적으로 조건에 따라 값을 정할 때 활용
- 삼항 연산자로 부르기도 함.
- 조건문을 한줄로 쓰는 표현(간단한 조건문일때 한줄로 표현)
- True인 경우 값 if 조건 else False인 경우 값
ex) `value = num if num >= 0 else -num`
    - 절댓값을 저장하기 위한 코드

#### 조건 표현식 실습 문제
- 다음의 코드와 동일한 조건 표현식을 작성하시오.
  
![조건 표현식 실습](../image/20230117/20230117_8.PNG)

~~~python
num = 2
result = '홀수입니다.' if num % 2 else '짝수입니다.'
print(result)
~~~

## 3. 반복문

### 반복문 기본
- 특정 조건을 만족할 때까지 같은 동작을 계속 반복하고 싶을 때 사용
  
![반복문](../image/20230117/20230117_9.PNG)

- while 문(특정한 조건을 알고 있을 때)
  - 종료 조건에 해당하는 코드를 통해 반복문을 종료시켜야 함.
- for 문(반복의 횟수를 알고 있을 때)
  - 반복 가능한 객체를 모두 순회하면 종료(별도의 종료 조건이 필요 없음)
- 반복 제어
  - break, continue, for-else

### while문
- while문은 조건식이 참인 경우 반복적으로 코드를 실행
  - 조건이 참인 경우 들여쓰기 되어 있는 코드 블록이 실행됨
  - 코드 블록이 모두 실행되고, 다시 조건식을 검사하며 반복적으로 실행됨.
  - while문은 무한 루프를 하지 않도록 종료 조건이 반드시 필요
  
![while](../image/20230117/20230117_10.PNG)

### 복합 연산자(In-Place Operator)
- 복합 연산자는 연산과 할당을 합쳐 놓은 것 
  - 예시) 반복문을 통해서 개수를 카운트 하는 경우

![ipo](../image/20230117/20230117_11.PNG)

### for문
- for문은 스퀸스(string,tuple,list,range)를 포함한 순회 가능한 객체의 요소를 모두 순회
  - 처음부터 끝까지 모두 순회하므로 별도의 종료 조건이 필요하지 않음
- Iterable
  - 순회 할 수 있는 자료형(string,tuple,list,dict,range,set 등)
  - 순회형 함수(range,enumerate)

![for문](../image/20230117/20230117_12.PNG)

### for문을 이용한 문자열(string) 순회
- 사용자가 입력한 문자를 한 글자씩 출력하시오

![for문순회](../image/20230117/20230117_13.PNG)

### 딕셔너리(Dictionary) 순회
- 딕셔너리는 기본적으로 key를 순회하며, key를 통해 값을 활용

![딕셔너리순회](../image/20230117/20230117_14.PNG)

### 추가 메서드를 활용한 딕셔너리(Dictionary) 순회
- 추가 메서드를 활용하여 순회할 수 있음.
  - keys() : Key로 구성된 결과
  - values() : value로 구성된 결과
  - item() : (Key,value)의 튜플로 구성된 결과

### 이터레이터(enumerate) 순회
- enumerate()
  - 인덱스와 객체를 쌍으로 담은 열거형(enumerate) 객체 반환
    - (index, value)형태의 tuple로 구성된 열거 객체를 반환
`print(list(enumerate(menbers, start=1)))`
기본값은 0, start를 지정하면 해당 값부터 순차적으로 증가

![열거순회](../image/20230117/20230117_15.PNG)

### List Comprehension
- 표현식과 제어문을 통해 특정한 값을 가진 리스트를 간결하게 생성하는 방법
  
![리스트](../image/20230117/20230117_16.PNG)

#### List Comprehension 예시
- 1~3의 세제곱의 결과가 담긴 리스트를 만드시오.
~~~python
cubic_List = []
for number in range(1,4):
    cubic_List.append(number**3)
print(cubic_List)

=>

cubic_List = [number**3 for number in range(1,4)]
print(cubic_List)
~~~

### Dictionary Comprehension
- 표현식과 제어문을 통해 특정한 값을 가진 딕셔너리를 간결하게 생성하는 방법
  
![딕셔너리](../image/20230117/20230117_17.PNG)

#### Dictionary Comprehension 예시
- 1~3의 세제곱의 결과가 담긴 딕셔너리를 만드시오.
~~~python
cubic_dict = {}

for nuber in range(1,4):
    cubic_dict[number] = number ** 3
print(cubic_dict)

=>

cubic_dict = {nuber: number ** 3 for number in range(1,4)}
print(cubic_dict)
~~~

### 반복문 제어
- break
  - 반복문을 종료
- continue
  - continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
- for-else
  - 끝까지 반복문을 실행한 이후 else문 실행
    - break를 통해 중간에 종료되는 경우 else문은 실행되지 않음
- pass
  - 아무것도 하지 않음(문법적으로 필요하지만, 할 일이 없을 때 사용)

![반복문 제어](../image/20230117/20230117_18.PNG)

#### break
- break문을 만나면 반복문은 종료됨
~~~python
for i in range(10):
    if i > 1:
        print('0과 1만 필요해!')
        break
    print(i)

'''
0
1
0과 1만 필요해!
'''
~~~
**특정 조건에 반복문을 종료시키기 위해서는 break!**

#### continue
- continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
~~~python
for i in range(6):
    if i % 2 == 0:
        continue
    print(i)

'''
1
3
5
'''
~~~
**continue를 만나면, 이후 코드인 print(i)가 실행되지 않고 바로 다음 반복을 시행**

#### pass
- 아무것도 하지 않음
  - 특별히 할 일이 없을 때 자리를 채우는 용도로 사용
  - **반복문 아니여도 사용 가능**
~~~python
for i in range(4):
    if i == 2:
        pass
    print(i)

'''
0
1
2
3
'''
~~~

#### else
- 끝까지 반복문을 실행한 이후에 esle문 실행
~~~python
for chr in 'apple':
    if char == 'b':
        print('b!')
        break
else:
    print('b가 없습니다.')

**else 문은 break로 중단되었는지 여부에 따라 실행**
~~~

### 20230118

## 0. 들어가기전에...

### 함수
- 함수를 왜 사용할까요?
  - **Decomposition(분해)**
    - 기능을 분해
    - 재사용 가능하게 만듬
      - 간결하고 이해하기 쉽게 만듬!
  - **Abstraction(추상화)**
    - 복잡한 내용을 모르더라도 사용할 수 있도록(스마트폰)
    - 재사용성과 가독성, 생산성
    - 사실 내부 구조를 변경할게 아니라면 몰라도 무방
      - 그것이 함수의 장점이자 프로그래밍의 매력
      - 스마트폰의 원리를 잘 몰라도 우리는 잘 사용할 수 있음

## 1. 함수 기초

### 함수의 종류
- 함수는 크게 3 가지로 분류
  - 내장 함수 
    - 파이썬에 기본적으로 포함된 함수
  - 외장 함수
    - import 문을 통해 사용하며, 외부 라이브러리에서 제공하는 함수
  - 사용자 정의 함수
    - 직접 사용자가 만드는 함수

### 함수의 정의
- 함수(Function)
  - 특정한 기능을 하는 코드의 조각(묶음)
  - 특정 코드를 매번 다시 작성하지 않고, 필요시에만 호출하여 간편히 사용

![함수 정의](../image/20230118/20230118_1.PNG)

### 함수 기본 구조
- 선언과 호출(define & call)
- 입력(Input)
- 문서화(Docstring)
- 범위(Scope)
- 결과값(Output)

![함수 기본구조](../image/20230118/20230118_2.PNG)

### 선언과 호출(define & call)

- 함수의 선언은 **def 키워드** 를 활용함
- 들여쓰기를 통해 **Function body**(실행될 코드 블록)를 작성함
  - Docstring은 함수 body앞에 선택적으로 작성가능
  - 작성시에는 반드시 첫번째 문장에 문자열 ''''''
  - 함수는 parameter를 넘겨줄 수 있음
  - 함수는 동작 후에 return을 통해 결과값을 전달함
### 함수의 정의
- 함수를 사용하기 위해서는 먼저 함수를 **정의**해야 함

![함수 정의](../image/20230118/20230118_3.PNG)

### 선언과 호출(define & call)
- 함수는 함수명()으로 호출하여 사용
  - parameter가 있는 경우, 함수명(값1,값2, …)으로 호출
- 함수는 호출해야만 작동함
- 함수는 호출되면 코드를 실행하고 return 값을 반환하고 종료

![선언 호출](../image/20230118/20230118_4.PNG)

#### 함수 실행 순서 예시
- 이 코드의 실행 결과는 왜 9 일까요?
~~~Python
num1 = 0
num2 = 1

def func1(a,b):
    return a+b

def func2(a,b):
    return a-b

def func3(a,b):
    return func1(a,5) + func2(5,b)

res = func3(num1,num2)

print(res)
'''
9
'''
~~~

## 2. 함수의 결과값(Output)

### 값에 따른 함수의 종류
- Void function
  - 명시적인 return 값이 없는 경우, None을 반환하고 종료
- Value returning function
  - 함수 실행 후, return문을 통해 값 반환
  - return을 하게 되면, 값 반환 후 **함수가 바로 종료**

#### ***주의*** - print vs return
- print 함수와 return의 차이점
  - print를 사용하면 호출될 때마다 값이 출력됨(주로 테스트를 위해 사용)
  - 데이터 처리를 위해서는 return 사용

![void vs Value return](../image/20230118/20230118_5.PNG)

- REPL(Read-Eval-Print Loop)환경에서는 마지막으로 작성된 코드의 리턴 값을 보여주므로 같은 동작을 하는 것으로 착각 할 수 있음
  
### 두개 이상의 값 반환
- 아래 코드의 문제점은 무엇일까?
~~~python
def mandp(x,y):
    return x-y
    return x*y

y = mandp(4,5)
print(y) # -1
~~~
- **return은 항상 하나의 값 만을 반환**

두 개 이상의 값을 반환하는 방법은?
- 반환 값으로 튜플 사용
~~~python
def mandp(x,y):
    return x-y, x*y

y = mandp(4,5)
print(y) # (-1,20)
print(type(y)) # <class 'tuple>
~~~

### 함수 반환 정리
- return X → None
- return O → 하나를 반환
  → 여러개를 원한다면, Tuple 활용(혹은 list와 같은 컨테이너 사용)

## 3. 함수의 입력(Input)

### Parameter와 Argument
- Parameter : 함수를 정의할 때, 함수 내부에서 사용되는 변수
- Argument : 함수를 호출 할 때, 넣어주는 값

![parameter,argumnet](../image/20230118/20230118_6.PNG)

### Argument
- Argument란?
  - 함수 호출 시 함수의 prarameter를 통해 전달되는 값
  - Argument는 소괄호 안에 할당 `func_name(argument)`
    - 필수 Argument : 반드시 전달되어야 하는 argument
    - 선택 Argument : 값이 전달하지 않아도 되는 경우는 기본값이 전달

#### Positional Arguments
- 기본적으로 함수 호출 시 Argument는 위치에 따라 함수 내에 전달 됨

![Positional Arguments](../image/20230118/20230118_7.PNG)

#### Keyword Arguments
- 직접 변수의 이름으로 특정 Argument를 전달할 수 있음
- Keyword Argument 다음에 Positional Argument를 활용할 수 없음

![Keyword Arguments](../image/20230118/20230118_8.PNG)

#### Default Arguments Values
- 기본값을 지정하여 함수 호출 시 argument 값을 설정하지 않도록 함
  - 정의된 것 보다 더 적은 개수의 argument 들로 호출될 수 있음
  
![Default Arguments Values](../image/20230118/20230118_9.PNG)

## 4. Python의 범위(Scope)

### Python의 범위(Scope)
- 함수는 코드 내부에 local scope를 생성하며, 그 외의 공간인 global scope로 구분

- scope
  - global scope : 코드 어디에서든 참조할 수 이쓴ㄴ 공간
  - local scope : 함수가 만든 scople. 함수 내부에서만 참조 가능
- variable
  - global variable : global scope에 정의된 변수
  - local variable : local scope에 정의된 변수

### 변수 수명주기(lifecycle)
- 변수는 각자의 생명주기(lifecycle)가 존재
  - built-in scope
    - 파이썬이 실행된 이후부터 영원히 유지
  - global scope
    - 모듈(~~.py)이 호출된 시점 이후 혹은 인터프리터가 끝날 때까지 유지
  - local scope
    - 함수가 호출될 때 생성되고, 함수가 종료될 때까지 유지
- 변수가 사라진다 : 더이상 접근을 할 수 없다.

ex)
~~~python
def func1():
  print('func1 시작')

  def func2():
    print('func2 시작')
    print('func2 끝')
    return

  func2()
  return

'''
# 함수를 실행하지 않음
'''
~~~
ex2)
~~~python
x='글로벌!' # global space에 속함
def func1():

  def func2():
    print(x)

  func2()

func1()

'''
글로벌!
'''
~~~

![Default Arguments Values](../image/20230118/20230118_10.PNG)
<span style="color:lightgreen">a는 Local scope에서만 존재</span>

### 이름 검색 규칙(Name Resolution)
- 파이썬에서 사용되는 이름(식별자)들은 이름공간(namespace)에 저장되어 있음
cf) Namespace

(1) built-in : 이미들어있는 NS

(2) global : 파이썬 안에서 생성된 NS

(3) enclosed : 함수 중첩시 함수와 함수사이에 있는 NS

(4) local - 함수 안쪽에 생성되는 NS

- 아래와 같은 순서로 이름을 찾아나가며, **LEGB Rule**이라고 부름
  - Local scope : 지역 범위(현재 작업중인 범위)
  - Enclosed scope : 지역 범위 한 단계 위 범위
  - Global scope : 최상단에 위치한 범위
  - Built-in scope : 모든 것을 담고 있는 범위(정위하지 않고 사용할 수 있는 모든 것)
- **함수 내에서는 바깥 Scope의 변수에 접근 가능하나 수정 할 수 없음**
- **같은 이름으로 정의되면 LEGB순으로 찾아 할당한다.**
  
순서 : L -> E -> G -> B

![NS 순서](../image/20230118/20230118_11.PNG)

### global 문
- 현재 코드 블록 전체에 적용되며, 나열된 식별자(이름)이 global variable임을 나타냄
  - global에 나열된 이름은 같은 코드 블록에서 global 앞에 등장 할 수 없음
  - global에 나열된 이름은 parameter, for 루프 대상, 클래스/함수 정의 등으로 정의되지 않아야 함.

#### global 예시
![global 예시](../image/20230118/20230118_12.PNG)

- `global x` - local 변수 값을  global 변수 값으로 바꿈
  
#### global 관련 에러
![global관련에러](../image/20230118/20230118_13.PNG)

### nonlocal
- global을 제외하고 가장 가까운(둘러싸고 있는) scope의 변수를 연결하도록 함
  - nonlocal에 나열된 이름은 같은 코드 블록에서 nonlocal앞에 등장 할 수 없음
  - nonlocal에 나열된 이름은 parameter, for 루프 대상, 클래스/함수 정의 등으로 정의되지 않아야 함
- global과는 달리 이미 존재하는 이름과의 연결과 가능함

#### nonlobal 예시
![nonlobal 예시](../image/20230118/20230118_14.PNG)

#### nonlocal, global 비교
![global관련에러](../image/20230118/20230118_15.PNG)

### 함수의 범위 주의
- 기본적으로 함수에서 선언된 변수는 local scope에 생성되며, 함수 종료 시 사라짐
- 해당 scope에 변수가 없는 경우 LEGB rule에 의해 이름을 검색함
  - 변수에 접근은 가능하지만, 해당 변수를 수정할 수 없음
  - 값을 할당하는 경우 해당 scope의 이름공간에 새롭게 생성되기 때문
  - <span style="color:lightgreen">단, 함수 내에서 필요한 상위 scope 변수는 argument로 넘겨서 활용할 것</span>

- 상위 scope에 있는 변수를 수정하고 싶다면, global, nonlocal 키워드를 활용 가능
  - 단, 코드가 복잡해지면서 변수의 변경을 추적하기 어렵고, 예기치 못한 오류가 발생
  - 가급적 사용하지 않는 것을 권장하며, <span style="color:lightgreen">함수로 값을 바꾸고자 한다면 항상 argument로 넘기고 리턴 값을 사용 하는 것을 추천</span>
  
### 20230119

## 1. 함수의 응용

### 내장함수(Built-in Functions)
- 파이썬 인터프리터에는 항상 사용할 수 있는 많은 함수와 형(type)이 내장되어 있음

### map
`map(function, iterable)`
- 순회 가능한 데이터구조(iterable)의 모든 요소에 함수(function)적용하고, 그 결과를 map object로 반환

![map 함수](../image/20230119/20230119_1.PNG)

### map 활용 사례
- 알고리즘 문제 풀이시 input 값들을 숫자로 바로 활용하고 싶을 때 

![map 함수](../image/20230119/20230119_2.PNG)

### filter
`filter(function,iterable)`
- 순회 가능한 데이터구조(iterable)의 모든 요소에 함수(function)적용하고, 그 결과가 True인 것들을 filter object로 반환

![filter](../image/20230119/20230119_3.PNG)

### zip
`zip(*iterables)`
- 복수의 iteable을 모아 튜플을 원소로 하는 zip object를 반환

![zip](../image/20230119/20230119_4.PNG)

### lambda 함수
`lambda[parameter]:표현식`
- 람다 함수
  - 표현식을 계산한 결괏값을 반환하는 함수로, 이름이 없는 함수여서 익명 함수라고도 불림
- 특징
    - return문을 가질 수 없음
    간편 조건문 외 조건문이나 반복문을 가질 수 없음
- 장점
  - 함수를 정의해서 사용하는 것보다 간결하게 사용 가능
  - def를 사용할 수 없는 곳에서도 사용 가능

  cf) 함수에 소괄호, 뒤에 소괄호 하면 함수 실행됨
    - ex) `(lambda x:x*x)()`

### 재귀 함수(recursive function)
- 자기 자신을 호출하는 함수
- 무한한 호출을 목표로 하는 것이 아니며, 알고리즘 설계 및 구현에서 유용하게 활용
  - 알고리즘 중 재귀 함수로 로직을 표현하기 쉬운 경우가 있음(예-점화식)
  - 변수의 사용이 줄여들며, 코드의 가독성이 높아짐
- 1개 이상의 base case(종료되는 상황)가 존재하고, 수렴하도록 작성

#### 예시
- Factorial 

![팩토리얼](../image/20230119/20230119_5.PNG)

### 재귀 함수 주의 사항
- 재귀 함수는 base case에 도달할 때까지 함수를 호출함
- 메모리 스택이 넘치게 되면(stack overflow) 프로그램이 동작하지 않게 됨
- 파이썬에서는 최대 깊이(maximum recursion depth)가 1,000번으로, 호춧 횟수가 이를 넘어가게 되면 Recursion Error 발생

### 반복문과 재귀 함수 비교
- 알고리즘 자체가 재귀적인 표현이 자연스러운 경우 재귀함수를 사용함.
- 재귀 호출은 변수 사용을 줄여줄 수 있음.
- 재귀 호출은 입력 값이 커질 수록 연산 속도가 오래 걸림.

## 2. 패킹/언패킹(Packing/Unpacking)

### 패킹/언패킹 연산자(Operator) *
- 모든 시퀀스형(리스트, 튜플 등)은 패킹/언패킹 연산자 `*`를 이용하여 객채의 패킹 또는 언패킹이 가능

#### 패킹
- 대입문의 좌변 변소에 위치
- 우변의 객체 수가 좌변의 변수 수보다 많을 경우 객체를 순서대로 대입 
- 나머지 항목들은 모두 별 기호 표시된 변수에 리스트로 대입

![패킹](../image/20230119/20230119_6.PNG)

#### 언패킹
- argument 이름이 *로 시작하는 경우, argument unpacking이라 함.
  - *패킹의 경우, 리스트로 대입
  - *언패킹의 경우 튜플 형태로 대입

![언패킹](../image/20230119/20230119_7.PNG)

- 별표(*) 연산자가 곱셈을 의미하는지 패킹/언패킹 연산자인지 구분
  - 패킹/언패킹 연산자 *
    - *가 대입식의 좌측에 위치하는 경우
    - *가 단항 연산자로 사용되는 경우
      - 단항 연산자 : 하나의 항을 대상으로 연산이 이루어지는 연산자

  - 산술연산자로서의 *
    - *가 이항연산자로 사용되는 경우
      - 이항 연산자 : 두 개의 항을 대상으로 연산이 이루어지는 연산자

### 가변인자(*args)
- 가변인자란?
  - 여러 개의 Positional Argument를 하나의 필수 parameter로 받아서 사용
- 가변인자는 언제 사용하는가?
  - 몇 개의 Positional Argument를 받을지 모르는 함수를 정의할 때 사용

![가변인자](../image/20230119/20230119_8.PNG)

#### 패킹/언패킹
- 가변 인자를 이해하기 위해서는 패킹, 언패킹을 이해해야 함.
- 패킹
  - 여러 개의 데이터를 묶어서 변수에 할당하는 것
~~~python
numbers = (1,2,3,4,5) #패킹
print(numbers) #(1,2,3,4,5)
~~~
- 언패킹
  - 시퀀스 속의 요소들을 여러 개의 변수에 나누어 할당하는 것
~~~python
numbers = (1,2,3,4,5)
a,b,c,d,e = numbers #언패킹
print(a,b,c,d,e) # 1 2 3 4 5
~~~
- 언패킹시 변수의 개수와 할당하고자 하는 요소의 갯수가 동일해야 함
- 언패킹시 왼쪽의 변수에 asterisk(*)를 붙이면, 할당하고 남은 요소를 리스트에 담을 수 있음

### Asterrisk(*)와 가변 인자
- *는 스퀀스 언패킹 연산자로고도 불리며, 말 그대로 스퀀스를 풀어 헤치는 연산자
  - 주로 튜플이나 리스트를 언패킹하는데 사용
  - *를 활용하여 가변 인자를 만들 수 있음

![가변인자2](../image/20230119/20230119_9.PNG)

#### 가변인자 예시

![가변인자예시](../image/20230119/20230119_10.PNG)

![가변인자예시2](../image/20230119/20230119_11.PNG)

### 가변 키워드 인자(**kwargs)
- 몇 개의 키워드 인자를 받을지 모르는 함수를 정의할 때 유용
- **kwargs는 **딕셔너리로 묶여 처리**되며, parameter에 **를 붙여 표현

![가변키워드인자](../image/20230119/20230119_12.PNG)

#### 가변 키워드 인자 예시 

![가변키워드예시](../image/20230119/20230119_13.PNG)

![가변키워드인자](../image/20230119/20230119_14.PNG)

## 3. 모듈
- 다양한 기능을 하나의 파일로 (모듈, module)
- 다양한 파일을 하나의 폴더로(패키지, package)
- 다양한 패키지를 하나의 묶음으로(라이브러리, library)
- 이것을 관리하는 관리자(pip)
- 패키지의 활용 공간(가상환경)

### 모듈
  - 특정 기능을 하는 코드를 파이썬 파일(.py) 단위로 작성한 것
- 패키지
  - 특정 기능과 관련된 여러 모듈의 집합
  - 패키지 안에는 또 다른 서브 패키지를 포함

- 모듈과 패키지 불러오기
~~~python
import module
from module import var, function, Class
from module import *

from package import module
from package.module import var, function, Class
~~~

- 파이썬에 기본적으로 설치된 모듈과 내장 함수

#### 파이썬 패키지 관리자(pip)
- pPyPI(Python Package Index)에 저장된 외부 패키지들을 설치하도록 도와주는 패키지 관리 시스템
- 패키지 설치
  - 최신 버전 / 특정 버전 / 최소 버전을 명시하여 설치 할 수 있음
  - 이미 설치되어 있는 경우 이미 설치되어 있음을 알리고 아무것도 하지 않음

~~~bash
$ pip install SomePackage
$ pip install SomePackage ==1.0.5
$ pip install SomePackage>=1.0.4
~~~
- 패키지 삭제
~~~bash
$ pip uninstall SomePackage
~~~
- 패키지 목록 및 특정 패키지 정보
~~~bash
$ pip list
$ pip show SomePackage
~~~
- 패키지 관리하기
  - 아래의 명령어들을 통해 패키지 목록을 관리[1]하고 설치할 수 있음[2]
  - 일반적으로 패키지를 기록하는 파일의 이름은 requirements.txt로 정의함
  
~~~bash
$ pip freeze > requirements.txt
$ pip install -r requirements.txt
~~~

### 패키지
- 패키지는 여러 모듈 / 하위 패키지로 구조화
  - 활용 예시: package.module
- ahems vhfejdpsms __ init __.py 를 만들어 패키지로 인식
  -Python 3.3 부터는 파일이 없어도 되지만, 하위 버전 호환 및 프레임워크 등에서의 동작을 위해 파일을 생성하는 것을 권장

![패키지만들기](../image/20230119/20230119_15.PNG)

### 가상환경
- 파이썬 표준 라이브러리가 아닌 외부 패키지와 모듈을 사용하는 경우 모두 pip를 통해 설치 해야 함
- 복수의 프로젝트를 하는 경우 버전이 상이 할 수 있음
- 이러한 경우 가상환경을 만들어 프로젝트별로 독립적인 패키지를 관리 할 수 있음

- 가상환경을 만들고 관리하는데 사용되는 모듈
- 특정 디렉토리에 가상 환경을 만들고, 고유한 파이썬 패키지 집합을 가질 수 있음
  - 특정 폴더에 가상 환경이(패키지 집합 폴더 등) 있고
  - 실행 환경에서 가상환경을 활성화 시켜
  - 해당 폴더에 있는 패키지를 관리/사용함

#### 가상환경 생성
  - 가상환경을 생성하면, 해당 디렉토리에 별도의 파이썬 패키지가 설치됨
  $ python -m wenw <폴더명>

#### 가상환경 활성화/비활성화 

![가상환경](../image/20230119/20230119_16.PNG)


## 데이터구조

### 데이터 구조?
- 데이터 구조(Data Structure)
  - 여러 데이터를 효과적으로 사용, 관리하기 위한 구조
  - 파이썬에는 대표적으로 List,Tuple, Dict, Set 등의 데이터 구조가 있음
  - 타입과도 비슷함 "데이터 + 연산"
### 자료 구조
  - 컴퓨터 공학에서는 '자료구조'라고 함
  - 각 데이터의 효율적인 저장, 관리를 위한 구조를 나눠 놓은 것
![자료구조](../image/20230125/20230125_1.PNG)

### 데이터 구조 활용하기
- 데이터 구조를 활용하기 위해서는 메서드(method)를 사용
  - 메서드는 클래스 내부에 정의한 함수, 사실상 함수 동일
  - 쉽게 설명하자면 객체의 기능(추후 객체 지향 프로그래밍에서 학습)
  
![데이터구조](../image/20230125/20230125_2.PNG)

#### 데이터 구조 활용 예시
~~~python
List.append(10)
String.split()
etc...
~~~

### 파이썬 공식 문서의 표기법
- python 구문이 아니며, 문법을 표현하기 위한 것임
  
![표기법](../image/20230125/20230125_3.PNG)


## 순서가 있는 데이터 구조

### 문자열(String)
- 문자열들의 나열(sequence of characters)
  - 모든 문자는 str 타입(변경 불가능한 immutable)
- 문자열은 작은 따옴표(')나 큰 따옴표(")를 활용하여 표기
  - 문자열을 묶을 때 동일한 문장부호 활용
  - PEP8에서는 소스코드 내에서 하나의 문장 부호를 선택하여 유지하도록 함
  - 
![문자열](../image/20230125/20230125_4.PNG)

#### 문자열 조회/탐색 및 검증 메서드
![문자열조회 메서드](../image/20230125/20230125_5.PNG)

### 문자열 조회/탐색
- `.find(x)`
- x의 첫번째 위치를 반환. 없으면 -1을 반환함.(오류가 나지 않음)
~~~python
print('apple'.find('p')) # 1
print('apple'.find('k')) # -1
~~~
- `.index(x)`
- x의 첫번째 위치를 반환. 없으면 오류 발생.
~~~python
print('apple'.index('p')) # 1
print('apple'.index('k')) # ValueError : ~~~
~~~

#### 문자열 변경 메서드(S는 문자열)

![문자열 변경 메서드](../image/20230125/20230125_6.PNG)

- 문자열은 불변형인데, 문자열 변경이 되는 이유?
    - -> 기존의 문자열을 변경하는 게 아니라, 변경된 문자열을 새롭게 만들어서 반환

- 문자열 변경
- `.replace(old,new[,count])`
- 바꿀 대상 글자를 새로운 글자로 바꿔서 반환
- count를 지정하면, 해당 개수만큼만 시행

- `.strip([chars])`
- 특정한 문자들을 지정하면,
  - 양쪽을 제거하거나(strip), 왼쪽을 제거하거나(lstrip), 오른쪽을 제거(rstrip)
- 문자열을 지정하지 않으면 공백을 제거함

- `.split(sep=None, maxsplit=-1)`
- 문자열을 특정한 단위로 나눠 리스트로 반환
  - sep이 None이거나 지정되지 않으면 연속된 공백문자를 단일한 공백문자로 간주하고, 선행/후행 공백은 빈 문자열에 포함시키지 않음.
  - maxsplit이 -1인 경우에는 제한이 없음.
  



### 리스트(List)
### 튜플(Tuple)


!Quiz

주어진 문자열에서 숫자, 문자, 기호가 각각 몇개인지 판단하는 함수를 작성해보세요

!Anw

~~~python
def check(input_str):
  char_count = 0
  digit_count = 0
  symbol_count = 0

  for char in input_str:
    if char.isalpha():
        char_count += 1
    elif char.isdigit() :
        digit_count +=1
    else :
        symbol_count +=1

  return (char_count, digit_count, symbol_count)
~~~

## 순서가 없는 데이터

### 셋(set)
- Set이란 중복되는 요소가 없이, 순서에 상관없는 데이터들의 묶음
  - 데이터의 중복을 허용하지 않기 때문에 중복되는 원소가 있다면 하나만 저장
  - 순서가 없기 때문에 인덱스를 이용한 접근 불가능
- 수학에서의 집합을 표현한 컨테이너
  - 집합 연산이 가능(여집합을 표현하는 연산자는 별도로 존재 X)
  - 중보된 값이 존재하지 않음
- 담고 있는 요소를 삽입 변경, 삭제 가능 -> 가변 자료형(muutable)
 
![셋 메서드](../image/20230126/20230126_1.PNG)

#### 추가 및 변경
`.add(elem)`
- 셋에 값을 추가
  
`.update(*others)`
- 여러 값을 추가

#### 요소 삭제
`.remove(elem)`
- SET에서 삭제하고, 없으면 KeyError

`.discard(elem)`
- SET에서 삭제하고, 없어도 에러가 발생하지 않음

#### 삭제
`.pop()`
- 임의의 원소를 제거해 반환

`.clear()`
- 모든 항목을 제거

#### 집합관련 함수
`s.isdisjonit(t)`
- SET s가 SET t의 서로 같은 항목을 하나라도 갖고 있지 않는 경우, True반환(서로소)

`s.issubset(t)`
- SET s가 SET t의 하위 SET인 경우, True반환 

`s.issuperset(t)`
- SET s가 SET t의 상위 SET인 경우, True반환 
### 딕셔너리(Dict)
- 키-값(Key-value)쌍으로 이뤄진 자료형
- Dictionary 의 키(key)
  - key는 변경 불가능한 데이터(immutable)만 활용가능
    - string,integer,float,boolean,tuple,range
- 각 키의 값(values)
  - 어떤 형태든 관계없음

![딕셔너리 메소드](../image/20230126/20230126_2.PNG)

#### 조회
`.get(key[,default])`
- key를 통해 value를 가져옴
- keyErroe가 발생하지 않으며, default값을 설정할 수 있음(기본 : None)

#### 추가 및 삭제
`.pop(key[,default])`
- key가 딕셔너리에 있으면 제거하고 해당 값을 반환
- 그렇지 않으면 default를 반환
- default값이 없으면 KeyError

`.update()`
- 값을 제공하는 key,value로 덮어씁니다.



## 얕은 복사와 깊은 복사(shallow Copy & Deep Copy)

### 복사 방법
#### 할당(Assignment)
- 대입 연산자(=)
  - 리스트 복사 확인하기
  - 대입연산자를 통한 복사는 해당 객체에 대한 객체 참조(주소값)를 복사
  
#### 얕은 복사(Shallow copy)
- Slice 연산자 활용하여 같은 원소를 가진 리스트지만 연산된 결과를 복사(다른 주소값)
- 주의사항 : 복사하는 리스트의 원소가 주소를 참조하는 경우

#### 깊은 복사(Deep copy)

- import copy
- 리스트 복사 확인하기

#### 결론
- 리스트를 복사하고 싶다는 욕망이 든다면! 무조건 print찍어볼 것 !(혹은 디버깅 툴로 리스트 변화를 확인할 것)
- 그냥 모두 copy.deepcopy() 쓰면 되는거 아닌가요? -> 메모리 용량 증가, 컴퓨터 입장도 생각해줍시다..

#### 얕은복사 vs 깊은 복사
- 얕은 복사과 깊은 복사 모두 객체를 복사하긴한다. 하지만 얕은 복사의 경우 저장된 데이터들까지 복사를 하진 않기때문에 서로가 영향을 주고 받으며, 완전히 독립적인 객체로 만들기 위해서는 깊은 복사가 필요한 것이다.

마지막으로 정리를 해보면,

- 대입문을 통한 복사는 단순 복제(동일한 객체를 참조)
- 얕은 복사는 껍데기만 복사, 내용은 동일한 객체를 참조
- 깊은 복사는 껍데기를 복사하고 내용도 재귀적으로 복사


##  객체 지향 프로그래밍

### 객체 지향 프로그래밍이란?
- 객체 지향 프로그래밍 : 컴퓨터 프로그래밍의 패러다임 중 하나이다.
- 객체 지향 프로그래밍은 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위, 즉 "객체"들의 모임으로 파악하고자 하는 것이다. 각각의 객체는 메세지를 주고받고, 데이터를 처리 할 수 있다.

- 연결된 유기체가 아니라 독립적으로 보는거지!

#### 객체 지향 프로그래밍이란?
  - 프로그램을 여러 개의 독립된 객체들과 그 객체 간의 상호작용으로 파악하는 프로그래밍 방법
  
![객체지향](../image/20230130/20230130_1.PNG)

#### 객체 지향 프로그래밍이 필요한 이유
- 현실 세계를 프로그램 설계에 반영(추상화)

### 객체 지향의 장점 / 단점
#### 장점
- 객체는 잘 만들어놓으면 계속해서 재사용이 가능
- 객체는 그 자체로 데이터와 행동이 정의됨(독립적) == 개발자가 내부 구조를 몰라도 그냥 가져다가 다른 객체와 조립하면서 개발이 가능
- 객체 단위로 모듈화시켜 개발할 수 있으므로 많은 인원이 참여하는 대규모 소프트웨어 개발 가능
- 개발 용이성, 유지 보수 편의성, 신뢰성을 바탕으로 생산성이 대폭 증가!

#### 단점
- 설계 시 많은 노력과 시간이 필요함
  - 다양한 객체들의 상호 작용 구조를 만들기 위해 많은 시간과 노력이 필요
- 실행 속도가 상대적으로 느림
  - 절차 지향 프로그래밍이 컴퓨터의 처리구조와 비슷해서 실행 속도가 빠름

### OOP 기초
#### 객체
- 객체 : 컴퓨터 과학에서 객체 또는 오브젝트는 클래스에서 정의한 것을 토대로 메모리에 할당된 것으로 프로그램에서 사용되는 데이터 또는 식별자에 의해 참조되는 공간을 의미하며, 변수, 자료 구조, 함수 또는 메서드가 될 수 있다.
- 속성(데이터)과 행동(메서드)으로 구성된 모든 것
-  파이썬의 모든 것이 객체
-  객체의 특징
   -  타입 : 어떤 연선자와 조작이 가능한가?
   -  속성 : 어떤 상태를 가지는가?
   -  조작법 : 어떤 행위를 할 수 있는가?

### OOP 문법
- 클래스 정의 `class MyClass:`
- 인스턴스 생성 `my_instance = MyClass()`
- 메서드 호출 `my_instance.my_method()`
- 속성 접근 `my_instance.my_attribute`

비유 : 클래스(붕어빵 틀)을 가지고 인스턴트(붕어빵)을 생성한다.
클래스 : 객체들의 분류 / 설계도(class)
인스턴스 : 하나하나의 실체 / 예(instance
)
![클래스vs인스턴트](../image/20230130/20230130_2.PNG)

#### 객체 비교하기
- == 
  - 동등한(equal)
  - 변수가 참조하는 객체가 동등한(내용이 같은) 경우 True
  - 두 객체가 같아 보이지만 실제로 동일한 대상을 가리키고 있다고 확인해 준 것은 아님(내용이 같은지만 확인)
- is
  - 동일한(identical)
  - 두 변수가 동일한 객체를 가리키는 경우 True

#### 속성
- 특정 데이터 타입/클래스의 객체들이 가지게 될 상태/데이터를 의미
- 클래스 변수 / 인스턴스 변수가 존재

#### 인스턴스와 클래스 간의 이름 공간(namespace)
- 클래스를 정의하면, 클래스와 해당하는 이름 공간 생성
- 인스턴스를 만들면, 인스턴스 객체가 생성되고 이름 공간 생성
- 인스턴스에서 특정 속성에 접근하면, 인스턴스-클래스 순으로 탐색
#### 인스턴스 변수
- 인스턴스 변수
  - 인스턴스가 개인적으로 가지고 있는 속성
  - 각 인스턴스의 고유한 변수
- 생성자 메서드(__init__)에서 self.<name> 으로 정의
- 인스턴스가 생성된 이후 <instance>.<name>으로 접근 및 할당

#### 클래스 변수
- 클래스 변수
  - 한 클래스의 모든 인스턴스가 공유하는 값을 의미
  - 같은 클래스의 인스턴스들은 같은 값을 갖게 됨
  - 예) 특정 사이트의 User 수 등은 클래스 변수를 사용해야 함

### OOP 메서드
### 메서드
- 특정 데이터 타입/클래스의 객체에 공통적으로 적용 가능한 행위(함수)
- 메서드의 종류 
  - 인스턴스 메서드
  - 클래스 메서드
  - 정적 메서드

### 인스턴스 메서드
  (우리가 대부분 사용하는 메서드!)
- 인스턴스 변수를 사용하거나, 인스턴스 변수에 값을 설정하는 메서드
- 클래스 내부에 정의되는 메서드의 기본
- 호출 시, 첫번째 인자로 인스턴스 자기자신(self)이 자동으로 전달됨
#### self
- 인스턴스 자기자신
- 파이썬에서 인스턴스 메서드는 호출 시 첫번째 인자로 인스턴스 자신이 전달되게 설계
  - 매개변수 이름으로 self를 첫번째 인자로 정의 
  - 다른 단어를 써도 작동하지만, 파이썬의 암묵적인 규칙
#### 매직 메서드
(특별한 인스턴스 메서드)
- Bouble underscore(__)가 있는 메서드는 특수한 동작을 위해 만들어진 메서드로, 스페셜 메서드 혹은 매직 메서드라고 불림
- 특정 상황에 자동으로 불리는 메서드
- 예시 : __str__(self), __init__(self), __It__(self,other) 등
- 객체의 특수 조작 행위를 지정(함수, 연산자 등)
  -  __str__ : 이 객체를 문자열로 표현하면 어떻게 표현할지를 지정
     -  print 함수 등에서 객체를 출력하면 자동으로 호출되는 메서드
  - __gt__ : 부등호 연산자

#### 생성자 메서드
- 인스턴스 객체가 생성될 때 자동으로 호출되는 메서드
- 인스턴스 변수들의 초기화 
  - 인스턴스 생성
  - __init__메서드 자동 호출
- 인스턴스를 만들때~~ 무언가 하고 싶다면?!
 
### 클래스 메서드
- 클래스가 사용할 메서드
- @classmethod 데코레이터를 사용하여 정의
- 호출 시, 첫번째 인자로 클래스(cls)가 전달됨
- 
#### 데코레이터
(파이썬의 핵심 기능 중 하나!)
- 함수를 어떤 함수로 꾸며서 새로운 기능을 부여
- @데코레이터(함수명) 형태로 함수 위에 작성
- 순서대로 적용 되기 때문에 작성 순서가 중요
- 데코레이터를 활용하면 쉽게 여러 함수를 원하는대로 변경할 수 있음
  
### 클래스 메서드와 인스턴스 메서드
- 클래스 메서드 -> 클래스 변수 사용
- 인스턴스 메서드 -> 인스턴스 변수 사용
- 그렇다면 인스턴스 변수, 클래스 변수 모두 사용하고 싶다면?
  - 클래스는 인스턴스 변수 사용이 불가능
  - **인스턴스 메서드는 클래스 변수, 인스턴스 변수 둘 다 사용이 가능**

#### 스태틱 메서드
- 스태틱 메서드
  - 인스턴스 변수, 클래스 변수를 전혀 다루지 않는 메서드
- 언제 사용하는가?
  - 속성을 다루지 않고 단지 기능(행동)만을 하는 메서드를 정의할 때, 사용
- 인스턴스 변수, 클래스 변수 아무것도 사용하지 않을 경우에 사용
  - 즉, 객체 상태나 클래스 상태를 수정할 수 없음
  - @staticmethod 데코레이터를 사용하여 정의
- 일반 함수처럼 동작하지만, 클래스의 이름공간에 귀속됨
  - 주로 해당 클래스로 한정하는 용도로 사용
  
![스태틱](../image/20230130/20230130_3.PNG)

### 메서드 정리
- 인스턴스 메서드
  - 메서드를 호출한 인스턴스를 의미하는 self 매개 변수를 통해 인스턴스를 조작
- 클래스 메서드
  - 클래스를 의미하는 cls 매개 변수를 통해 클래스를 조작
- 스태틱 메서드
  - 클래스 변수나 인스턴스 변수를 사용하지 않는 경우에 사용
    - 객체 상태나 클래스 상태를 수정할 수 없음
  
![정리](../image/20230130/20230130_4.PNG)


## 객체지향 프로그래밍

### 객체 지향의 핵심 4가지
- 추상화 : 핵심이 되는 부분만 추리기
- 상속 : 코드의 재사용성을 높힘, 기능을 확장
- 다형성 : 각자의 특성에 따라 다른 결과 만들기
- 캡슐화 : 데이터 보호하기

### 추상화
- 현실 세계를 프로그램 설계에 반영
  - 복잡한 것은 숨기고, 필요한 것만 드러내기
  - 공통 부분을 묶어주기

![추상화](../image/20230131/20230131_1.PNG)

### 상속
- 상속이란
  - 두 클래스 사이 부모 - 자식 관계를 정립하는 것
- 클래스는 상속이 가능함
  - 모든 파이썬 클래스는 object를 상속 받음

![상속1](../image/20230131/20230131_2.PNG)

- 하위 클래스는 상위 클래스에 정의된 속성, 행동, 관계 및 제약 조건을 모두 상속 받음
- 부모클래스의 속성, 메서드가 자식 클래스에 상속되므로, 코드 재 사용성이 높아짐

![상속2](../image/20230131/20230131_3.PNG)

#### 상속 관련 함수와 메서드
- `isinstance(object, classinfo)`
  - classinfo의 instance 거나 subcalss* 인 경우 True

![상속3](../image/20230131/20230131_4.PNG)

- `issubclass(class, classinfo)`
  - class가 classinfo의 subclass면 True
  - classinfo의 모든 항목을 검사

![상속4](../image/20230131/20230131_5.PNG)

- `super()`
  - 자식 클래스에서 부모클래스를 사용하고 싶은 경우

![상속5](../image/20230131/20230131_6.PNG)

#### 상속 정리
- 파이썬의 모든 클래스는 object로부터 상속됨
- 부모 클래스의 모든 요소(속성, 메서드)가 상속됨
- super()를 통해 부모 클래스의 요소를 호출할 수 있음
- 메서드 오버라이딩을 통해 자식 클래스에서 재정의 가능함
- 상속관계에서의 이름 공간은 인스턴스, 자식 클래스, 부모 클래스 순으로 탐색

#### 다중 상속
- 두 개 이상의 클래스를 상속 받는 경우
- 상속 받은 모든 클래스의 요소를 활용 가능함
- 중복된 속성이나 메서드가 있는 경우 상속 순서에 의해 결정됨

![상속6](../image/20230131/20230131_7.PNG)
![상속7](../image/20230131/20230131_8.PNG)

#### 상속 관련 함수와 메서드
- mro 메서드(Method Resolution Order)
  - 해당 인스턴스의 클래스가 어떤 부모 클래스를 가지는지 확인하는 메서드
  - 기존의 인스턴스 -> 클래스 순으로 이름 공간을 탐색하는 과정에서 상속관계가 있으면 인스턴스 -> 자식 클래스 -> 부모 클래스로 확장

### 다형성
- 다형성(Polymorphism)이란?
  - 여러 모양을 뜻하는 그리스어
  - 동일한 메서드가 클래스에 따라 다르게 행동할 수 있음을 의미
  - 즉, 서로 다른 클래스에 속해있는 객체들이 동일한 메세지에 대해 다른 방식으로 응답할 수 있음
#### 메서드 오버라이딩
- 상속받은 메서드를 재정의
  - 클래스 상속 시, 부모 클래스에서 정의한 메서드를 자식 클래스에서 변경
  - 부모 클래스의 메서드 이름과 기본 기능은 그대로 사용하지만, 특정 기능을 바꾸고 싶을 때 사용
  - 상속 받은 메서드를 재정의
    - 상속받은 클래스에서 같은 이름의 메서드로 덮어씀
    - 부모 클래스의 메서드를 싱핼시키고 싶은 경우 super를 사용

### 캡슐화
- 객체의 일부 구현 내용에 대해 외부로부터의 직접적인 액세스를 차단
  - 예시 : 주민등록번호
- 파이썬에서 암묵적으로 존재하지만, 언어적으로는 존재하지 않음
- 접근 제어자 종류
  - public Access Modifier 
    - 모두 가능
  - Protected Access Modifier
    - 상속받은 관계에서만 가능
  - Private Access Modifier
    - 나만 가능

- Public Member 
  - 언더바 없이 시작하는 메서드나 속성
  - 어디서나 호출이 가능, 하위 클래스 오버라이드 허용
  - 일반적으로 작성되는 메서드와 속성의 대다수를 차지
- Protected Member
  - 언더바 1개로 시작하는 메서드나 속성
  - 암묵적 규칙에 의해 부모 클래스 내부와 자식 클래스에서만 호출 가능
  - 하위 클래스 오버라이드 허용
- Private Member
  - 언더바 2개로 시작하는 메서드나 속성
  - 본 클래스 내부에서만 사용이 가능
  - 하위클래스 상속 및 호출 불가능(오류)
  - 외부 호출 불가능(오류)

- getter 메서드와 setter 메서드
- 변수에 접근할 수 있는 메서드를 별도로 생성
  - getter 메서드 : 변수의 값을 읽는 메서드
    - @property 데코레이터 사용
  - setter 메서드 : 변수의 값을 설정하는 성격의 메서드
    - @변수.setter 데코레이터 사용

## 에러와 예외처리

### 디버깅

#### 버그란?
- 최초의 버그는 1945년 프로그래밍 언어의 일종인 코볼 발명자 그레이스 호퍼가 발견
- 역사상 최초의 컴퓨터 버그는 Mark 2라는 컴퓨터 회로에 벌레인 나방이 들어가 합선을 일으켜 비정상적으로 동작
- 이때부터 소프트웨어에서 발생하는 문제를 버그라고 부름

#### 디버깅의 정의
- 잘못된 프로그램을 수정하는 것을 디버깅이라함 de(없앤다)+bugging(버그)
- 에러 메세지가 발생하는 경우
  - 해당 하는 위치를 찾아 메세지를 해결
- 로직 에러가 발생하는 경우
  - 명시적인 에러 메세지 없이 예상과 다른 결과가 나온 경우
    - 정상적으로 동작하였던 코드 이후 작성된 코드를 생각해봄 
    - 전체 코드를 살펴봄.. 등등
  
- print 함수 활용
  - 특정 함수 결과, 반복/조건 결과 등 나눠서 생각, 코드를 bisection으로 나눠서 생각
  - 개발 환경(text editor, IDE)등에서 제공하는 기능 활용 : breakpoint, 변수 조회 등
  - Python tutor 활용

### 문법 에러(Syntax Error)
- SyntaxError가 발생하면, 파이썬 프로그램은 실행이 되지 않음
- 파일이름, 줄번호, ^문자를 통해 파이썬이 코드를 읽어 나갈때(parser) 문제가 발생한 위치를 표현
- 줄에서 에러가 감지된 가장 앞의 위치를 가리키는 캐럿(caret)기호(^)를 표시
- Invalid syntax : 문법 오류
~~~python
while # SyntaxError : invalid syntax
~~~
- assign to literal : 잘못된 할당
~~~python
5=3 # SyntaxError : cannot assign to literal
~~~
- EOL(End of Line)
~~~python
print('hello
# SyntaxError : EOL while scanning string literal
~~~
- EOF(End of File)
~~~python
print(
# SyntaxError : inexpected EOF while parsing 
~~~
### 예외(Exception)
- 실행 도중 예상치 못한 상홍을 맞이하면, 프로그램 실행을 멈춤
  - 문장이나 표현식이 문법적으로 올바르더라도 발생하는 에러
- 실행 중에 감지되는 에러들을 예외라고 부름
- 예외는 여러 타입으로 나타나고, 타입이 메세지의 일부로 출력됨
- 모든 내장 예외는 Exception Class를 상속받아 이뤄짐
- 사용자 정의 예외를 만들어 관리할 수 있음

- ZeroDivisionError : 0으로 나누고자 할 때 발생 
~~~python
10/0 # ZeroDivisionError : division by zero
~~~
- NameError : namespace 상에 이름이 없는 경우
~~~python
print(name_error)
# NameError : name 'name_error' is not defined
~~~
- TypeError : 타입 불일치
~~~python
1 + '1' # TypeError : unsupported operand type(s) for +: 'int' and 'str'
round('3.5') # TypeError : type str doesn't define __round_-method
~~~
- TypeError : argument 누락
~~~python
divmod() #TypeError : divmod expected 2 argument, got 0

import random
random.sample()
#TypeError : sample() missing 2 required positional arguments : 'population' and 'k'
~~~
- TypeError : argument 개수 초과
~~~python
divmod(1,2,3) #TypeError : divmod expected 2 argument, got 3

import random
random.sample(range(3),1,2)
#TypeError : sample() takes 3 positional arguments but 4 were given
~~~
- TypeError : argument type 불일치
~~~python
import random
random.sample(1,2)
#TypeError : Population must be a sequence. For dicts or sets, use sorted(d).
~~~
- ValueError : 타입은 올바르나 값이 적절하지 않거나 없는 경우
~~~python
int('3.5') # ValueError : invalid literal for int() with base 10: '3.5'

range(3).index(6) # ValueError : 6 is not in range
~~~

- IndexError : 인덱스가 존재하지 않거나 범위를 벗어나는 경우 
~~~python
empty_list = []
empty_list[2]
# IndexError : list index out of range
~~~
- KeyError : 해당 키가 존재하지 않는 경우
~~~python
song = {'IU' : '좋은날'}
song['BTS'] #KeyError : 'BTS'
~~~

- ModuleNotFoundError
~~~python
inport ssafy #ModuleNotFoundError : No module named 'ssafy'
~~~

- ImportError : Module은 있으나 존재하지 않는 클래스/함수를 가져오는 경우
~~~python
from random inport samp
# ImportError : cannot import name 'smap' form 'random'(/usr/lib/...)
~~~

- KeyboradiInterrupt - 임의로 프로그램을 종료하였을 때

- IndentationError : Indentation이 적절하지 않는 경우
~~~python
for i in range(3):
  print(i) #IndentationError : expected an indented block
for i in range(3):
  print(i)
    print(i) #IndentationError : unexpected indent
~~~
![오류예외](../image/20230131/20230131_9.PNG)
- 예외처리를 할때는 작은 것 부터!
### 예외 처리
- try문(statement) / except 절(clause)을 이용하여 예외 처리를 할 수 있음
- try문
  - 오류가 발생할 가능성이 있는 코드를 실행
  - 예외가 발생되지 않으면, except 없이 실행 종료
- except 문
  - 예외가 발생하면, except 절이 실행
  - 예외 상황을 처리하는 코드를 받아서 적절한 조치를 취함

![예외처리](../image/20230131/20230131_10.PNG)

- 작성 방법
~~~python
try :
  try명령문
except 예외그룹-1 as 변수-1 :
  예외처리 명령문 1
except 예외그룹-2 as 변수-2 :
  예외처리 명령문 2
finally : <<< 선택사항
  finally명령문
~~~
- 주의 : try문은 반드시 한 개 이상의 except문이 필요

#### 예외 메시지 처리(as)
- as 키워드를 활용하여 원본 에러 메세지를 사용할 수 있음
  - 예외를 다른 이름에 대입

![예외 메시지 처리](../image/20230131/20230131_11.PNG)

#### 복수의 예외 처리 
- 발생 가능한 에러를 모두 명시
- 에러 별로 별도의 에러처리
- 순차적으로 수행됨으로, 가장 작은 범주부터 예외 처리를 해야함

### 예외처리 종합
- try
  - 코드를 실행함
- except 
  - try 문에서 예외가 발생 시 실행함
- else 
  - try 문에서 예외가 발생하지 않으면 실행함
- finally
  - 예외 발생 여부와 관계없이 항상 실행함