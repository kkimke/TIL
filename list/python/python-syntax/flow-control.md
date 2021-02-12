## ⚓ Flow control

- [if](#if)
- [for](#for)
- [while](#while)
<hr />

## if

```python
# 기본 형식

# True: 0이 아닌 수, 문자, 데이터가 들어있는 list 등
# False: 0, [], {}, ()등 빈 데이터

city = 'Newyork'

if city:
    print('You are in:', city)  # You are in Newyork
else:
    print('Let me know your city'.)
```

<br>

```python
# 관계 연산자 (>, >=, <, <=, ==, !=>)

x = 15
y = 10

print(x == y)  # False
print(x != y)  # True
print(x > y)   # True
print(x >= y)  # True
print(x < y)   # False
print(x <= y)  # False
```

<br>

```python
# 논리 연산자 (and, or, not)

a = 75
b = 10
c = 40

print(a > b and b > c)  # False
print(a > b or b > c)  # True
print(not a > b)  # False

print(not True)   # False
print(not False)  # True
```

```python
score1 = 95
score2 = 'A'

# 복수의 조건이 모두 참일때 실행 (and)
if score1 >= 90 and score2 == 'A':
    print('Pass')  # print
else:
    print('Fail')
```

```python
id1 = 'vip'
id2 = 'admin'
grade = 'platinum'

if id1 == 'vip' or id2 == 'admin':
    print('관리자 입장')  # print

if id2 == 'admin' and grade == 'platinum':
    print('최상위 관리자')  # print
```

<br>

```python
# 다중 조건문 (elif)

num = 95  # Grade : A

if num >= 90:
    print('Grade : A')
elif num >= 80:
    print('Grade : B')
elif num >= 70:
    print('Grade : C')
else:
    print('과락')
```

<br>

```python
# 중첩 조건문

grade = 'A'
total = 92  # 장학금 100%

if grade == 'A':
    if total >= 90:
        print('장학금 100%')
    elif total >=80:
        print('장학금 80%')
    else:
        print('장학금 50%')
else:
    print('장학금 없음')
```

<br>

```python
# in, not in

q = [10, 20, 30]
w = {70, 80, 90, 100}
e = {'name': 'Kim', 'city': 'Newyork', 'grade': 'A'}
r = (10, 12, 14)

print(15 in q)      # False
print(90 in w)      # True
print(12 not in r)  # False
print('name' in e)  # True
print('Kim' in e)   # False
print('Kim' in e.values())  # True
```

<hr />

## for

```python

```
