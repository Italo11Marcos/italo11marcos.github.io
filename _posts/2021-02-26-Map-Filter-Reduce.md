---
layout: post
title: Map, Filter, Reduce
categories: python
tags: [python, iterables, procedural, lambda, map, filter, reduce, funções]
toc: true
---

# Map, Filter e Reduce

Hoje vamos falar sobre três funções que são paradigmas da programação funcional, ou seja, permitem que você escreva menos e melhor.

## Map

`Map` é uma função `built-in`, ou seja, uma função já integrada ao python, você não precisa importar para poder utilizar.

O `Map` permite aplicar uma função para cada item em um iterável, como por exemplo `lista` ou um `dicionário`. Possui a seguinte sintaxe:

`map(func, *iterables)`

Para entendermos melhor, vamos para alguns exemplos.

```
lower_words = ['abacaxi', 'abacate', 'alface', 'mandioca', 'banana']
upper_words = []

for word in lower_words:
    word_ = word.upper()
    upper_words.append(word_)

print(upper_words)

Output:
['ABACAXI', 'ABACATE', 'ALFACE', 'MANDIOCA', 'BANANA']
```

No código acima, transformamos todas as palavras para ficarem em sua forma maiúscula. Com map fazemos a mesma coisa e com menos linhas, vejamos:

```
lower_words = ['abacaxi', 'abacate', 'alface', 'mandioca', 'banana']

upper_words = list(map(str.upper, lower_words))

print(upper_words)

Output:
['ABACAXI', 'ABACATE', 'ALFACE', 'MANDIOCA', 'BANANA']
```

Utilizando `map` com `lambda`

```
numbers = [1, 2, 3, 4, 5]

new_numbers = list(map(lambda x: x * 5, numbers))

print(new_numbers)

Output:
[5, 10, 15, 20, 25]
```

Com dois iteráveis. No exemplo a seguir, passamos dois iteráveis como paramêtros. O que o código a seguir faz é fazer a potencialização  da lista `numbers` com a lista `powers`, ou seja, `1^2, 2^4, 3^4, 4^6 e 5^10`.

```
numbers = [1, 2, 3, 4, 5]
powers = [2, 4, 8, 6, 10]

new_numbers = list(map(pow, numbers, powers))

print(new_numbers)

Output:
[1, 16, 6561, 4096, 9765625]
```


## Filter

`Filter`, assim como o `map`, também é uma função `built-in`. Possui a seguinte sintaxe:

`filter(func, iterable)`

No entanto, ela aceita somente um iterável.

Como o próprio nome sugere, essa função filtra os iteráveis a partir da função definida.

Exemplo: Filtrar valores menores que 50 numa lista

```
ages = [65, 12, 57, 48, 55, 24, 90]

filtered_ages = list(filter(lambda x: x < 50, ages))

print(filtered_ages)

Output
[12, 48, 24]
```

Podemos também filtrar valores válidos

```
ages = [11, False, 18, 21, "", 12, 34, 0, [], {}]

filtered_ages = list(filter(None, ages))

print(filtered_ages)

Output
[11, False, 18, 21, "", 12, 34, 0, [], {}]
```

## Reduce

`Reduce`, diferentemente do `map` e `filter`, deve ser importada antes de usar.

`from functools import reduce`

Possui a seguinte sintaxe:

`reduce(func, iterable[, initial])`

Sendo `func` a função que irá iterar cada elemento cumulativamente. `iterable`, sendo o iterável e `initial`
o valor inicial. Ficará mais claro com exemplos.

`Reduce` reduz o iterável a um valor.

```
from functools import reduce

values = [1, 2, 3, 4, 5]

product_values = reduce(lambda x, y: x * y, values)

print(product_values)

Output
120
```

Exemplo com `initial`

```
from functools import reduce

values = [1, 2, 3, 4, 5]

product_values = reduce(lambda x, y: x * y, 10)

print(product_values)

Output
1200
```

## Referências

* [DigitalOcean Community Map](https://www.digitalocean.com/community/tutorials/how-to-use-the-python-map-function-pt)

* [DigitalOcean Community Filter](https://www.digitalocean.com/community/tutorials/how-to-use-the-python-filter-function-pt)

* [Learn Python](https://www.learnpython.org/en/Map,_Filter,_Reduce)
