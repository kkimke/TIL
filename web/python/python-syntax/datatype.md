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

## int & float

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
