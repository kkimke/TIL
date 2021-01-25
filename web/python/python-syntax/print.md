## separator 옵션

```python
print('P', 'Y', 'T', 'H', 'O', 'N')

# P Y T H O N
```

```python
print('P', 'Y', 'T', 'H', 'O', 'N', sep='')

# PYTHON
```

```python
print('010', '1234', '5678', sep='-')
print('python', 'google.com', sep='@')
# 010-1234-5678
# python@google.com
```

<br>

## end 옵션

```python
print('Welcome to', end=' ')
print('kkimke', end=' ')
print('Github')
# Welcome to kkimke Github
```

<br>

## format 사용 (digit, string, float)

```python
print('%s %s' % ('one', 'two'))  # only string
print('{} {}'.format('one', 'two'))  # whatever
print('{1} {0}'.format('one', 'two'))
# one two
# one two
# two one
```
