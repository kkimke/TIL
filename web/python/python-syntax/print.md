## separator 옵션

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

## end 옵션

```python
print('Welcome to', end=' ')
print('kkimke', end=' ')
print('Github')

#Welcome to kkimke Github
```

<br>

## format 사용 (string, digit, float)

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

## Reference

- [Inflearn 파이썬 입문](https://www.inflearn.com/course/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EC%9E%85%EB%AC%B8-%EC%9D%B8%ED%94%84%EB%9F%B0-%EC%98%A4%EB%A6%AC%EC%A7%80%EB%84%90/dashboard)
- [점프 투 파이썬](https://wikidocs.net/book/1)
