---
layout: post
title: Args e Kwargs 
categories: python
tags: [python, args, kwargs]
toc: true
---

*args e **kwargs Python

## *args
O argumento *args é usado para passar um número variável de argumentos para uma função.

    def my_function(*args):
	    print(args)

    my_function(1,8.4,'ola',8**2)
    Output: (1, 8.4, 'ola', 64)

    lista1 = [1, 'ola', 53]
    lista2 = [5, '+', 23]
    my_function(*lista1, *lista2)
    Output: (1, 'ola', 53, 5, '+', 23)

## **kwargs
O argumento **kwargs é usado para passar argumentos com palavras chaves, ou melhor dizendo, keywords. Com exemplo fica muito melhor para explicar:

    def my_function(**kwargs):
	    print(kwargs)

    my_function(nome="Italo", sobrenome="Marcos")
    Output: {'nome': 'Italo', 'sobrenome': 'Marcos'}


<b>Dica:</b> É melhor usar ``kwargs.get('key')`` a ``kwargs['key']``, pois se a keyword não existir, retorna ``None``

    def my_function(**kwargs):
        idade = kwargs.get('idade')
        ano = kwargs['ano']
        print(idade)
        print(ano)

    my_function(idade=23)
    Output: ano = kwargs['ano'] KeyError: 'ano'
                        
## Bonus: Desempacotamento de listas

Podemos 'desempacotar' listas. Só usar o ``*``. Com exemplos e testes você vai entender melhor.

    lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    n1, n2, n3, *n4n8, n9, n10 = lista
    print(n1, n2, n3, n4n8, n9, n10, sep="\n")

    Output:
    1
    2
    3
    [4, 5, 6, 7, 8]
    9
    10

## Refêrencias
* [Programiz](https://www.programiz.com/python-programming/args-and-kwargs)
* [Geek for Geeks](https://www.geeksforgeeks.org/args-kwargs-python/)