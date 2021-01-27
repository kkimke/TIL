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

<br>

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
