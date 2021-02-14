## ⚓ Data types

- [int & float](#int-float)
- [string](#string)
- [list](#list)
- [tuple](#tuple)
- [dictionary](#dictionary)
- [set](#set)
- [PRACTICE](#practice)

<hr />

## Python data type

```python
# int, float, complex
# bool
# str
# list, tuple, set, dict
```

```python
int_v = 7
float_v = 10.0
bool_v = True
str1 = 'Python'
str2 = 'Anaconda'
list_v = [str1, str2]
tuple_v = (3, 4, 5)
set_v = {6, 7, 8}
dict_v = {
    'name' : 'kkimke',
    'version': 2.0
}

print(type(int_v))  # <class 'int'>
print(type(float_v))  # <class 'float'>
print(type(bool_v))  # <class 'bool'>
print(type(str1))  # <class 'str'>
print(type(str2))  # <class 'str'>
print(type(list_v))  # <class 'list'>
print(type(tuple_v))  # <class 'tuple'>
print(type(set_v))  # <class 'set'>
print(type(dict_v))  # <class 'dict'>
```

<hr>

## int-float

### 숫자형 연산자

```python
# +, -, *, /
# //:몫, %:나머지
# abs(x):절댓값
# pow(x, y):거듭제곱 = x ** y
```

<br>

### 정수 (int)

```python
i = 30
i2 = -30
i3 = 99999999999999999999999999

# Python에서는 big int로 따로 처리하지 않고 동일하게 할당 가능
```

<br>

### 실수 (float)

```python
f = 0.999
f2 = 3.141592
f3 = -1.0
f4 = 3 / 9  # 0.333333333333333
```

<br>

### 형변환

```python
a = 3 + 1.9

print(a)  # 4.9
print(type(a))  # <class 'float'>

# 정수와 실수를 계산하면, 알아서 형변환이 일어나 계산되어 type도 바뀜
```

```python
a = 3.  # = 3.0
b = 6
c = .7  # = 0.7
d = 12.7

print(int(a))  # 3
print(float(b))  # 6.0
print(int(c))  # 0
print(int(d))  # 12
```

```python
print(int(True))  # 1
print(float(False))  # 0.0
print(complex(3))  # (3+0j)
print(complex('3'))  # (3+0j)  # Python이 내부적으로 문자형->숫자형으로 변환
print(complex(False))  # 0j
```

<br>

### 수치 연산 함수

```python
print(abs(-7))  # 7 (절댓값)
print(pow(5, 3))  # 125 (5의 3제곱)
print(5 ** 3)  # 125
```

<br>

### 외부 모듈

```python
import math

print(math.pi)  # 3.141592~ (원주율)
print(math.ceil(5.1))  # 6 (x이상의 수 중 가장 작은 정수)

# 계산을 내부에서 하지 않고, math라는 외부 모듈 가져와 pi, ceil 호출
```

<br>

### 지수 표현 방식

- e나 E 다음에 오는 수는 10의 지수부를 의미
  ex) 1e9 = 10의 9제곱 (1,000,000,000)
- 지수 표현 방식은 임의의 큰 수를 표현하기 위해 사용
- 최단 경로 알고리즘에서는 도달할 수 없는 노드에 대해 '최단 거리를 무한(INF)으로 설정', 이때 가능한 최댓값이 10억 미만이라면 INF의 값으로 1e9을 이용

```python
INF = 1e9

print(INF)  # 1000000000.0, 기본적으로 실수로 출력됨

INF = int(1e9)

print(INF)  # 1000000000
```

<br>

### 실수 표현 오차

- IEEE754 표준에서는 실수형을 저장하기 위해 4바이트 혹은 8바이트의 고정된 크기의 메모리를 할당
- 컴퓨터 시스템은 실수 정보를 표현하는 정확도에 한계를 가짐
- ex) 10진수 체계에서는 0.3과 0.6을 더한 값이 0.9로 정확히 떨어지나, 2진수 체계에서는 최대한 0.9에 가깝게 표현하나 미세한 오차 발생

```python
a = 0.3 + 0.6

print(a)  # 0.89999999999
```

```python
# round() 함수 이용

a = 123.456

print(round(a, 2))  # 123.46, 소수 셋째 자리에서 반올림
```

<hr>

## string

### 문자형

```python
str1 = "Python"
str2 = 'Python'
str3 = """Python"""
str4 = '''Python'''
```

### 빈 문자열

```python
str_1 = ""
str_2 = str()

print(type(str_1), len(str_1))
print(type(str_2), len(str_2))

# <class 'str'> 0
# <class 'str'> 0
```

### 멀티라인 입력

```python
multi_str = \
"""
string
multi line
test
"""

print(multi_str)

# string
# multi line
# test
```

<br>

### Escape string

```python
print('I\'m kkimke')  # I'm kkimke

'''
\n   개행
\t   탭
\\   문자
\'   문자
\"   문자
\000 널 문자
'''
```

### Raw string

```python
raw_s1 = r"D:\python\test"

print(raw_s1)  # D:\python\test

# escape코드가 적용되지 않도록 '있는 그대로' 출력
```

<br>

### 문자열 연산

```python
str_o1 = "python"
str_o2 = "apple"
str_o3 = "How are you doing"
str_o4 = "Seoul Daejeon Busan Jinju"

print(str_o1 * 3)        # pythonpythonpython
print(str_o1 + str_o2)   # pythonapple
print("y" in str_o1)     # True
print("z" in str_o1)     # False
print("P" not in str_o2) # True
```

<br>

### 문자열 형변환

```python
print(str(66), type(str(66)))       # 66 <class 'str'>
print(str(10.1), type(str(10.1)))   # 10.1 <class 'str'>
print(str(True), type(str(True)))   # True <class 'str'>
```

<br>

### 문자열 함수

```python
print("Capitalize: ", str_o1.capitalize())         # Capitalize: Python
print("endswith: ", str_o2.endswith("s"))          # endswith: False
print("replace: ", str_o1.replace("thon", "Good")) # replace: pyGood
print("sorted: ", sorted(str_o1))                  # ['h', 'n', 'o', 'p', 't', 'y']
print("split", str_o4.split(" "))                  # ['Seoul', 'Daejeon', 'Busan', 'Jinju']

# capitalize : 첫 글자를 대문자로
# endswith : 끝글자가 x로 끝나는지
# split : ""을 기준으로 특정 단어나 문장 분리
```

<br>

### 반복 (시퀀스)

```python
im_str = "Good Boy!"

print(dir(im_str))  # 속성값들 출력, __iter__있다면 반복(시퀀스) 가능

for i in im_str:
    print(i)

# G
# o
# o
# d
# ... 한 글자씩 슬라이스 되어 출력
```

<br>

### 슬라이싱

```python
str_s1 = "Nice Python"

print(len(str_s1))  # 11
print(str_s1[0:3])  # Nic
print(str_s1[5:11]) # Python

print(str_s1[5:])  # Python
print(str_s1[:len(str_s1)]  # Nice Python, str_s1[:11]과 동일
print(str_s1[:])  # Nice Python
print(str_s1[:len(str_s1)-1])  # Nice Pytho, str_s1[:10]과 동일

print(str_s1[1:4:2]  # ie, 2단위로
print(str_s1[1:9:2]  # iePt

print(str_s1[::2]  # Nc yhn
print(str_s1[::-1]  # nohtyP eciN
```

<br>

### 아스키 코드 & 유니코드

```python
a = "z"

print(ord(a))  # 122 (z에 해당하는 아스키 코드는 122번)
print(chr(122))  # z (아스키 코드 122번에 해당하는 문자는 z)
```

<hr>

## list

- 순서o, 중복o, 수정o, 삭제o

### 선언

```python
a = []
b = list()
c = [70, 75, 80, 85]
d = [1000, 10000, "Ace", "Base", "Captain"]   # 서로 다른 자료형
e = [1000, 10000, ["Ace", "Base", "Captain"]] # 리스트 안에 리스트 (중첩)
f = [21.42, "foobar", 3, 4, False, 3.14159]
```

<br>

### 인덱싱

```python
print("d - ", type(d), d)  # d - <class 'list'> [1000, 10000, 'Ace', 'Base', 'Captain']
print("d - ", d[1])  # d - 10000
print("d - ", d[0] + d[1] + d[1])  # d - 21000
print("d - ", d[-1])  # d - Captain
print("e - ", e[-1][1])  # e - Base

print(type(e[-1][1]))  # <class 'str'>
print(list(e[-1][1]))  # ['B', 'a', 's', 'e']
```

<br>

### 슬라이싱

```python
print("d - ", d[0:3])  # d - [1000, 10000, 'Ace']
print("d - ", d[2:]  # d - ['Ace', 'Base', 'Captain']
print("e - ", e[-1][1:3]  # e - ['Base', 'Captain']
```

<br>

### 리스트 연산

```python
print(c + d)  # [70, 75, 80, 85, 1000, 10000, 'Ace', 'Base', 'Captain']
print(c * 3)  # [70, 75, 80, 85, 70, 75, 80, 85, 70, 75, 80, 85]
print"test" + str(c[0]))  # test70, 바로 test와 c[0]를 더할 시 에러나므로 형변환시켜 계산
```

<br>

### 값 비교

```python
print(c[:3])  # [70, 75, 80]
print(c[3:])  # [85]
print(c == c[:3] + c[3:])  # True
```

<br>

### identity (id)

```python
temp = c
print(temp, c)
print(id(temp) == id(c))  # True # 즉 같은 id를 갖고, 한쪽이 바뀌면 다른쪽도
```

<br>

### 리스트 수정, 삭제

```python
c[0] = 4
print(c)  # [4, 75, 80, 85]

c[1:2] = ['a', 'b', 'c']
print(c)  # [4, a, b, c, 80, 85] # 두번째인 75자리에 a,b,c가 들어감

#만약 다음과 같은 경우였다면?
c[1:2] = [['a', 'b' ,'c']]
print(c)  # [4, ['a', 'b', 'c'], 80, 85] # 리스트 안에 리스트가 들어감

#만약 다음과 같은 경우였다면?
c[1] = ['a', 'b', 'c']
print(c)  # [4, ['a', 'b', 'c'], 80, 85], 리스트 중첩
```

<br>

### 리스트 함수

```python
a = [5, 2, 3, 1, 4]

a.append(10)
print('a- ', a)  # a- [5, 2, 3, 1, 4, 10], 끝에 값을 추가

a.sort()
print('a- ', a)  # a- [1, 2, 3, 4, 5, 10], 오름차순 정렬

a.reverse()
print('a- ', a)  # a- [10, 5, 4, 3, 2, 1], 기존값의 반대로 정렬

print('a- ', a.index(3))  # a- 3, '숫자3'의 인덱스 번호 (위치)

a.insert(2, 7)
print('a- ', a)  # a- [10, 5, 7, 4, 3, 2, 1], 2번째 '위치'에 7이라는 '값' 넣기

a.remove(10)
print('a- ', a)  # a- [5, 7, 4, 3, 2, 1]  , 10이라는 값 제거

a.pop()
print('a- ', a)  # a- [5, 7, 4, 3, 2], 끝 원소를 불러온 후, 제거

print('a -', a.count(4))  # 1, 리스트 안에 4가 몇개 있는지

ex = [8, 9]
a.extend(ex)
print('a- ', a)  # a- [5, 7, 4, 3, 2, 8, 9], a리스트 끝에 ex리스트[8,9]를 추가
```

<br>

### 삭제하는 법

```python
# (1) remove() : 원하는 값을 바로 삭제
# (2) pop() : 끝에 있는 값을 삭제
# (3) del : index번호로 삭제
power = [1, 2, 3, 4, 5]
del power[2]  # 2번 값을 삭제
# (4)
power[2:3] = []  # 2번 값을 삭제

# (5) 모두 삭제
power.clear() # -> 빈 list
```

```python
# python의 리스트에는 remove_all이 존재하지 않음

a = [1, 2, 3, 4, 5, 5, 5]
remove_set = {3, 5}
result = [i for i in a if i not in remove_set]

print(result)  # [1, 2, 4], 중복되는 5라는 값 모두 삭제됨
```

<br>

### 반복문 활용

```python
a = [5, 7, 4, 3, 2, 8, 9]

while a:
	data = a.pop()
	print(data)

# 9
# 8
# 2
# 3
# 4
# 7
# 5

# pop으로 끝에서부터 계속 꺼내 삭제, 비어있을때까지 반복
```

<br>

### 리스트 컴프리헨션

- 2차원 리스트를 초기화할때 효과적으로 사용

```python
# 0부터 9까지의 수를 포함하는 리스트

array = [i for i in range(10)]

print(array)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

```python
# 0부터 19까지의 수 중 홀수만 포함하는 리스트

array = [i for i in range(20) if i % 2 == 1]

print(array)  # [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
```

```python
# 1부터 9까지의 수들의 제곱 값을 포함하는 리스트

array = [i * i for i in range(1, 10)]

print(array)  # [1, 4, 9, 16, 25, 36, 49, 64, 81]
```

<hr>

## tuple

- 순서o, 중복o, 수정x, 삭제x
- packing & unpacking

### 선언

```python
a = (1, 2)  # 튜플 선언은 소괄호 안에, 괄호 생략 가능
b = 1,

print(type(a), type(b))  # <class 'tuple'> <class 'tuple'>

# 이때 원소가 하나일 경우 끝에 콤마,를 찍지 않으면 class가 int로 출력됨 주의 (원소가 두 개 이상일때는 상관없음)

c = (11, 12, 13, 14)
d = (100, 1000, 'Ace', 'Base', 'Captain')
e = (100, 1000, ('Ace', 'Base', 'Captain'))  # 중첩 가능
```

<br>

### 수정 불가

```python
d[0] = 1500  # 에러
```

<br>

### 인덱싱

```python
print('d- ', d[1])  # d- 1000
print('d- ', d[0] + d[1] + d[1])  # d- 2100
print('d- ', d[-1])  # d- Captain
print('e- ', e[-1])  # e- ('Ace', 'Base', 'Captain')
print('e- ', e[-1][1])  # e- Base
print('e- ', list(e[-1][1]))  # e- ('B', 'a', 's', 'e')

# tuple이 list로 변환되어, 문자 단위로 분해되어 출력됨
# list로 변환되었기 때문에 수정, 삭제 가능해짐
```

### 슬라이싱

```python
print('d- ', d[0:3])  # d- (100, 1000, 'Ace')
print('d- ', d[2:])  # d- ('Ace', 'Base', 'Captain')
print('e- ', e[2][1:3])  # e- ('Base', 'Captain')
```

<br>

### 튜플 연산

```python
print('c + d', c + d)  # c + d (11, 12, 13, 14, 100, 1000, 'Ace', 'Base', 'Captain')
print('c * 3', c * 3)  # c * d (11, 12, 13, 14, 11, 12, 13, 14, 11, 12, 13, 14)
```

<br>

### 튜플 함수

```python
a = (5, 2, 3, 1, 4)
print('a- ', a)
print('a- ', a.index(3))  # a- 2  # 숫자 3이 들어간 위치 : 인덱스 2
print('a- ', a.count(2))  # a- 1  # 숫자 2의 개수 : 1개
```

<br>

### 팩킹

- 하나로 묶는 것
- 인덱싱 가능, 괄호 생략 가능

```python
t = ('apple', 'banana', 'city', 'dinosaur')

print(t[0])  # apple
print(t[-1])  # dinosaur
```

### 언팩킹

- 반대로, 하나로 묶여있던 tuple을 풀어 각각 순서에 맞는 원소에 대입
- 괄호 생략 가능

```python
(x1, x2, x3, x4) = t

print(type(x1), type(x2), type(x3), type(x4))  # <class 'str'> <class 'str'> <class 'str'> <class 'str'>
print(x1, x2, x3, x4)  # apple banana city dinosaur
```

```python
t2 = 1, 2, 3  # packing
t3 = (4,)  # packing
(x1, x2, x3) = t2  # unpacking
x4, x5, x6 = 4, 5, 6  # unpacking

print(t2)  # (1, 2, 3)
print(t3)  # (4,)
print(x1, x2, x3)  # 1 2 3
print(x4, x5, x6)  # 4 5 6
```

<hr>

## dictionary

- 순서x, 키 중복x, 수정o, 삭제o

### 선언

```python
a = {'name': 'Kim', 'phone': '01012345678', 'fav': 'breads'}
b = {0: 'Hello Python'}  # 숫자 key 가능
c = {'arr': [1, 2, 3, 4]}  # key만 존재한다면 어떤 값도 가능
```

```python
# 3가지 방식
d = {
    'Name': 'kkimke',
    'City': 'Busan',
    'Age': 50,
    'Grade': 'A',
    'Status': True
}

e = dict([
    ('Name', 'kkimke'),
    ('City', 'Busan'),
    ('Age', 50),
    ('Grade', A),
    ('Status', True)
])

f = dict(
    Name='kkimke,
    City='Seoul',
    Age=33,
    Grade='A',
    Status=True
)
```

<br>

### 출력

```python
print(a['name'])  # Kim
print(a.get['name'])  # Kim

# 출력 결과 같음
# 그러나 만약 name1을 출력할 경우, 첫번째는 에러, 두번째는 None 출력됨(에러로 인해 흐름끊기지 않음)

print(b[0])  # Hello Pythohn
print(b.get(0))  # Hello Python
print(f.get('City'))  # Busan
print(f.get('Age'))  # 50
```

<br>

### key: value 추가

```python
a['address'] = 'Seoul'
print(a)  # {... 'address': 'Seoul'}

a['rank'] = [1, 2, 3]
print(a)  # {... 'rank': [1, 2, 3]}
```

<br>

### 길이 확인

```python
print(len(a))  # 5
print(len(b))  # 1
print(len(c))  # 1
print(len(d))  # 5
```

<br>

### 딕셔너리 함수

```python
# dict_key, dict_values, dict_items : 반복문(__iter__)에서 사용 가능

# key값들만 가져오는 함수 (dict_keys)
print(a.keys())
print(list(b.keys()))  # 리스트형태로 변환

# values값들만 가져오는 함수 (dict_values)
print(a.values())

# key와 values값 모두 가져오는 함수 (dict_items)
print(a.items())
```

<br>

### 삭제

```python
print(a.pop('name'))  # Kim
print(a)  # name: Kim가 선택되어 삭제됨

print(c.pop('arr'))  # [1, 2, 3, 4]
print(c)  # arr: [1, 2, 3, 4] 삭제되어 빈 {} 출력

print(f.popitem())  # pop은 직접 지정하는 반면, popitem은 임의로 아무 값(key: value)을 꺼내옴
print(f)  # 임의로(딕셔너리-순서x) 꺼낸값(key: value)이 삭제됨
```

<br>

### 조회

```python
print('birth' in a)  # True, birth라는 key가 a에 있는지 조회
print('city' in d)  # False, 소문자 c이므로
```

<br>

### 수정

```python
a['address'] = 'LA'
print(a)  # address 값 Seoul -> LA

a.update(fav='chicken')
print(a)  # fav 값 breads -> chicken

temp = {'address': 'Busan'}
a.update(temp)
print(a)  # adderss 값 LA -> Busan
```

<hr>

## set

- 순서x, 중복x

### 선언

```python
a = set()
b = set([1, 2, 3, 4])
c = set([1, 2, 'Pen', 'Cap', 'Plate'])
d = {'choco', 'cake', 'call', 'coupon'}  # {key없이 values만 나열하면 set}
e = {42, 'choco', (1, 2, 3), 3.14159}
```

### 중복 시

```python
f = set([1, 2, 3, 4, 4, 4])

print(f)  # {1, 2, 3, 4}, 중복 허용x
```

<br>

### 변환

- set -> tuple

```python
t = tuple(b)

print(type(t), t)  # <class 'tuple'> (1, 2, 3, 4)
print(t[0], t[1:3])  # 1 (2, 3)
```

- set -> list

```python
l = list(d)

print(type(l), l)  # <class 'list'> ['choco', 'cake', 'call', 'coupon']
```

<br>

### 길이

```python
print(len(a))  # 0, 공집합
print(len(b))  # 4
print(len(e))  # 4
```

<br>

### set 활용

- 기호와 함수로 호출해보자

```python
s1 = set([1, 2, 3, 4, 5, 6])
s2 = set([4, 5, 6, 7, 8, 9])

#교집합
print(s1 & s2)  # {4, 5, 6}
print(s1.intersection(s2))  # {4, 5, 6}

#합집합
print(s1 | s2)  # {1, 2, 3, 4, 5, 6, 7, 8, 9}
print(s1.union(s2))  # {1, 2, 3, 4, 5, 6, 7, 8, 9}

#차집합
print(s1 - s2)  # {1, 2, 3}
print(s1.difference(s2)  # {1, 2, 3}
```

<br>

### 중복 원소 확인

```python
# 교집합 확인
print(s1.isdisjoint(s2))  # False

# 부분집합 확인
small = {1, 2, 3}
big = {1, 2, 3, 4, 5}

print(small.issubset(big))  # True
print(big.issubset(small)  # False

print(big.issuperset(small))  # True
print(small.issuperset(big))  # False
```

<br>

### 추가 및 제거

```python
# list는 데이터 삽입할때 append, insert, index로 접근하지만, set에는 메소드가 있음

s1 = set([1, 2, 3, 4])

s1.add(5)
print(s1)  # {1, 2, 3, 4, 5}

s1.remove(2)
print(s1)  # {1, 3, 4, 5}

s1.discard(3)
print(s1)  # {1, 4, 5}

s1.clear()
print(s1)  # set(), 빈 집합 출력됨
```

<br>

## practice

홍길동씨의 평균 점수를 구해보자.
국어 : 80, 영어 : 75, 수학 : 55

```python
a = 80
b = 75
c = 55

print((a + b + c) / 3)

# 70
```

<br>

자연수 13이 홀수인지 짝수인지 판별할 수 있는 방법을 말해보자.

```python
num = 13
if num % 2 == 0:
    print('even')
else:
    print('odd')

# odd
```

<br>

홍길동 씨의 주민등록번호는 881120-1068234이다.
이를 연월일(YYYYMMDD) 부분과 그 뒤의 숫자 부분으로 나누어 출력해 보자.

```python
hong = '881120-1068234'
hong_first = hong[:6]
hong_second = hong[7:]

print(hong_first)   # 881120
print(hong_second)  # 1068234
```

<br>

주민등록번호 뒷자리의 맨 첫번째 숫자인 '성별을 나타내는 숫자'를 출력해보자.
pin = '881120-1068234'

```python
pin = '881120-1068234'
print(pin[7])  # 1 (남자)
```

<br>

a = 'a:b:c:d'
이 문자열을 replace 함수를 사용하여 a#b#c#d로 바꾸어 출력해 보자.

```python
a = 'a:b:c:d'
print(a.replace(':', '#'))

# a#b#c#d
```

<br>

[1, 3, 5, 4, 2] 리스트를 내장함수를 사용하여 [5, 4, 3, 2, 1]로 만들어 보자.

```python
a = [1, 3, 5, 4, 2]
a.sort()     # [1, 2, 3, 4, 5]
a.reverse()  # [5, 4, 3, 2, 1]
print(a)
```

<br>

['Life', 'is', 'too', 'short'] 리스트를
join 함수를 사용하여 Life is too short 문자열로 만들어 출력해 보자.

```python
a = ['Life', 'is', 'too', 'short']
b = ' '.join(a)
print(b)

# Life is too short
```

<br>

(1, 2, 3)이라는 튜플에 더하기(+)를 사용하여 4라는 값을 추가해 (1, 2, 3, 4)로 만들어 보자.

```python
a = (1, 2, 3)
a = a + (4,)
print(a)

# 1, 2, 3, 4
# tuple은 값을 변경할 수 없다. 다만 새로운 tuple인 (4, )를 생성하여 a에 대입할 수 있다.
```

<br>

pop함수를 사용하여 딕셔너리 a에서 'B'에 해당되는 값을 추출해 보자.
a = {'A':90, 'B':80, 'C':70}

```python
a = {'A': 90, 'B': 80, 'C': 70}
b = a.pop('B')
print(b)  # 80
print(a)  # {'A':90, 'C':70}
```

<br>

집합 자료형의 특징을 사용하여 a 리스트에서 중복 숫자를 제거해 보자.
a = [1, 1, 1, 2, 2, 3, 3, 3, 4, 4, 5]

```python
a = [1, 1, 1, 2, 2, 3, 3, 3, 4, 4, 5]
a_set = set(a)  # {1, 2, 3, 4, 5}
a_list = list(a_set)
print(a_list)  # [1, 2, 3, 4, 5]
```

<br>

파이썬은 동일한 값에 여러 개의 변수를 선언할 수 있다.
a, b 변수 선언 후 a의 두 번째 요솟값을 변경하면 b값은 어떻게 될까?

```python
a = b = [1, 2, 3]
a[1] = 4
print(b)

# [1, 4, 3]
# a의 index1인 2자리에 4를 넣으면, a는 [1, 4, 3]이 되고, b는 a와 동일한 리스트 객체를 가리키므로 결과값이 같다.
```
