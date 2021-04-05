---
layout: post
title: List Comprehension
categories: python
tags: [python, lists comprehension, procedural]
toc: true
---

`List Comprehension` é uma maneira interessante e bem poderosa de criar uma lista a partir de outra utilizando uma única linha.

Vamos que dizer que precisamos multiplicar os elementos da lista numbers por 2. Podemos fazer da seguinte forma:

```
numbers = [1, 2, 3, 4, 5]
example = []
for num in numbers:
    example.append(num * 2)
print(example)
Output:
[2, 4, 6, 8, 10]
```

Com list comprehension ficaria assim:

```
numbers = [1, 2, 3, 4, 5]
example = [num * 2 for num in numbers]
print(example)
Output:
[2, 4, 6, 8, 10]
```

`if` e `else` com `list comprehension`

```
numbers = list(range(1,21))
odd_numbers = [num for num in numbers if num % 2 != 0]
print(odd_numbers)
Output:
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
```

Dois `for` com `list comprehension`
```
matriz = [[1, 2], [3, 4], [5, 6], [7, 8]]
transposta = [[row[i] for row in matriz] for i in range(2)]
print(transposta)
Output:
[[1, 3, 5, 7], [2, 4, 6, 8]]
```

## Referências
* [LearnPython](https://www.learnpython.org/en/List_Comprehensions)
