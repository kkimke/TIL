## print

### separator 옵션

```python
print('P', 'Y', 'T', 'H', 'O', 'N')

#P Y T H O N
```

```python
print('P', 'Y', 'T', 'H', 'O', 'N', sep='')

#PYTHON
```

```python
print('010', '1234', '5678', sep='-')
print('python', 'google.com', sep='@')

#010-1234-5678
#python@google.com
```

<br>

### end 옵션

```python
print('Welcome to', end=' ')
print('kkimke', end=' ')
print('Github')

#Welcome to kkimke Github
```

<br>

### format 사용 (string, digit, float)

```python
print('%s %s' % ('one', 'two'))  # only string
print('{} {}'.format('one', 'two'))  # whatever
print('{1} {0}'.format('one', 'two'))

#one two
#one two
#two one
```

<br>

### %s 문자열

```python
print("%10s" % ("happy"))
print("%10s" % ("happyday"))

print("{:>10}".format("happy"))
print("{:>10}".format("happyday"))

#     happy
#  happyday
#     happy
#  happyday
```

```python
print("%-10s" % ("happy"))
print("{:10}".format("happyday"))

#happy     출력
#happyday  출력
```

```python
print("{:_>10}".format("happy"))
print("{:$>10}".format("happy"))
print("{:O>10}".format("happy"))

#_____happy
#$$$$$happy
#00000happy
```

```python
print("{:^10}".format("happy"))

#   happy  출력 (중앙정렬)
```

```python
print("%5s" % ("pythonstudy"))
print("%.5s" % ("pythonstudy"))

#pythonstudy (5자리 확보후 길면 그대로 출력)
#pytho (5자리 확보후 길면 절삭됨)
```

```python
print("{:10.5}".format("pythonstudy"))

#pytho     출력
```

<br>

### %d 정수

```python
print("%d %d" % (1, 2))
print("{} {}".format(1, 2))

#1 2
#1 2
```

```python
print("%4d" % (42))
print("%4d" % (42424242))
print("{:4d}".format(42))

#  42
#42424242
#  42

# 마찬가지로 4자리 확보후 길면 그대로 출력
# 문자열의 경우와 다르게, %d는 :d라고 명시해줘야 함
```

<br>

### %f 실수

```python
print("%f" % (3.141414141414))
print("%1.8f" % (3.141414141414))
print("{:f}".format(3.141414141414))

# 3.141414
# 3.14141414
# 3.141414

# %f는 기본적으로 소수점아래 6자리까지 출력됨
# %1.8은 정수 1자릿수, 소수 8자릿수 의미
```

```python
print("%06.2f" % (3.141592653589793))
print("{:06.2f}".format(3.141592653589793))

# 003.14
# 003.14

# 정수 6자릿수, 소수 2자릿수
# 즉 6자리 확보 후 소수 2자리를 출력하고, 나머지는 0으로 채움 (.도 한자리를 차지)
```

<br>

### 진수 변환

```python
# 파이썬의 숫자 표현은 10진수 형태
# 다른 진수로 표현하려면 다음과 같은 접두어 사용

# 2진수 : 0b
# 8진수 : 0o
# 16진수 : 0x
```

```python
# 10진수 -> 2, 8, 16진수

# 2진수 : bin()
# 8진수 : oct()
# 16진수 : hex()

bin(10)  # 0b1010
oct(10)  # 0o12
hex(10)  # 0xa

format(10, '#b')  # 0b1010
format(10, '#o')  # 0o12
format(10, '#x')  # 0xa
format(10, '#X')  # 0XA (대문자)

format(10, 'b')  # 1010
format(10, 'o')  # 12
format(10, 'x')  # a
format(10, 'X')  # A (대문자)
```

```python
# 2, 8, 16진수 -> 10진수

int('0b1010', 2)  # 10
int('0o12', 8)  # 10
int('0xa', 16)  # 10
```

<hr>

## Variable

### 기본 선언

```python
n = 70

print(n)  # 70
print(type(n))  # <class 'int'>
```

<br>

### 동시 선언

```python
x = y = z = 800

print(x, y, z)  # 800 800 800
```

<br>

### 재선언

```python
let = 10
let = 'change value'

print(let)  # change value
print(type(let))  # <class 'str'>
```

```python
n = 777
m = n
m = 400

print(m, n)  # 400 777
```

<br>

### identity (고유값)

```python
m = 800
n = 655

print(id(m))  # 1427246049552
print(id(n))  # 1427246049584
print(id(m) == id(n))  # False
```

```python
m = 800
n = 800

print(id(m))  # 1427246049552
print(id(n))  # 1427246049552
print(id(m) == id(n))  # True

# python 엔진은 똑같은 변수를 '동일한 값'으로 간주하고 동일한 id를 부여 (python의 효율성)
```

<br>

## 변수 네이밍 규칙

### 선언법

```python
# Camel Case : variableLikeThis
# Pascal Case : VariableLikeThis
# Snake Case : variable_like_this

# possible
age = 1
Age = 2
aGe = 3
AGE = 4
a_g_e = 5
_age = 6
age_ = 7
_AGE_ = 8
```

<br>

### 예약어

```python
# 예약어는 변수명 불가능

# Python reserved words
False def if raise None del import return True elif in try
and else is while as except lambda with assert finally
nonlocal yield break for not class from or continue global pass
```
