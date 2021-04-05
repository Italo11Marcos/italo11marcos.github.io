---
layout: post
title: Python Exceptions
categories: python
tags: [python, exceptions, error]
toc: true
---

Quando estamos programando, sempre nos deparamos com erros. Esses erros podem ser um `syntax error` ou `exception`. 

`Syntax errors` ocorrem quando escrevemos algo que o parser não consegue identificar. Vejamos o código abaixo:
```
print('python'}

Output:
SyntaxError: closing parenthesis '}' does not match opening parenthesis '('
```
Está ocorrendo um `syntax error`, indicando que estou fechando um `(` com `}`.

`Exception errors` ocorrem quanto um código com a sintaxe correta gera algum erro ao ser executado. Vejamos o código abaixo:
```
print(5 / 0)

Output:
ZeroDivisionError: division by zero
```
Está ocorrendo um `exception error`, indicando que estou tentando dividir um número por 0.

## Raise
Podemos utilizar `raise` para indicar um erro a qualquer momento.
```
x = 56
if x < 100:
    raise Exception('x não deve ser menor que 100')

Output:
Traceback (most recent call last):
  File "<pyshell#6>", line 2, in <module>
    raise Exception('x não pode ser menor que 100')
Exception: x não pode ser menor que 100
```

## Assert
Podemos utilizar `assert` para indicar um erro se certa condição for atendida.
```
x = 57:
assert x % 2 != 1, "x deve ser par"

Output:
Traceback (most recent call last):
  File "<pyshell#9>", line 1, in <module>
    assert x % 2 != 1, "x deve ser par"
AssertionError: x deve ser par
```

## Try e except
Podemos utilizar `try` e `except` que é basicamente executar o código no `try` e no `except`, retornar uma exceção.
```
def divide(x, y):
    return x/y

try:
    print(divide(x=5, y=0))
except AssertionError as error:
    print(error)

Output:
ZeroDivisionError: division by zero
```

## Else
Podemos utilizar o `else` com `try` e `except` se quisermos que alguma ação seja executada se nenhum error for lançado.
```
def divide(x, y):
    return x/y

try:
    print(divide(x=5, y=3))
except AssertionError as error:
    print(error)
else:
    print("OK")

Output:
1.6666666666666667
OK
```

## Finally
Podemos utilizar o ``finally`` com `try` e `except` se quisermos que alguma ação seja executada independente do que tenha ocorrido anteriormente.
```
def divide(x, y):
    return x/y

try:
    print(divide(x=5, y=0))
except AssertionError as error:
    print(error)
else:
    print("OK")
finally:
    print("Fim")

Output:
ZeroDivisionError: division by zero
Fim
```

## Referências:
* [Real Python](https://realpython.com/python-exceptions/)
* [Geeks for Geeks](https://www.geeksforgeeks.org/python-exception-handling/)
* [Python Doc](https://docs.python.org/3/tutorial/errors.html)