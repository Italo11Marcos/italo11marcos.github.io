---
layout: post
title: RegEX Python
categories: python
tags: [python, RegEX, Espressões Regulares]
toc: true
---

RegEX Python - Expressões Regulares com Python.

## Introdução

Expressão Regular ou RegEX é uma forma de identificar cadeias de caracteres de forma concisa e flexível em uma sequência de caracteres.

O Python já vem com um módulo padrão, ``re``, sendo necessário somente importar:

    import re

## Funções

<table>
    <tr>
        <td>Função</td>
        <td>Descrição</td>
    </tr>
    <tr>
        <td>findall</td>
        <td>Retorna uma lista com todas as ocorrências</td>
    </tr>
    <tr>
        <td>search</td>
        <td>Retorna um  Match object da ocorrência na string</td>
    </tr>
    <tr>
        <td>sub</td>
        <td>Substitui uma ou ocorrências na string</td>
    </tr>
    <tr>
        <td>split</td>
        <td>Retorna uma lista com a string dividida para cara ocorrência</td>
    </tr>
</table>

## Meta Caracteres

São caracteres que representam alguma coisa

<table>
    <tr>
        <td>Character</td>
        <td>Descrição</td>
        <td>Exemplo</td>
    </tr>
    <tr>
        <td>[]</td>
        <td>Conjunto de caracteres</td>
        <td>"[a-z]"</td>
    </tr>
    <tr>
        <td>\</td>
        <td>Para "escapar" um caractere especial</td>
        <td>"&lt;\/div&gt;"</td>
    </tr>
    <tr>
        <td>.</td>
        <td>Qualquer caractere (menos nova linha)</td>
        <td>"lo..m"</td>
    </tr>
    <tr>
        <td>^</td>
        <td>Começa com</td>
        <td>"^ola"</td>
    </tr>
    <tr>
        <td>$</td>
        <td>Termina com</td>
        <td>"mundo$"</td>
    </tr>
    <tr>
        <td>*</td>
        <td>Zero ou mais sequências</td>
        <td>"a*"</td>
    </tr>
    <tr>
        <td>+</td>
        <td>Um ou mais ocorrências</td>
        <td>"a+"</td>
    </tr>
    <tr>
        <td>{n}</td>
        <td>N ocorrências</td>
        <td>"it{5}"</td>
    </tr>
    <tr>
        <td>|</td>
        <td>Ou</td>
        <td>"loren|ipsum"</td>
    </tr>
    <tr>
        <td>()</td>
        <td>Divide em grupos</td>
        <td>"&lt;[h123]{2}&gt;(.*?)&lt;\/[h123]{2}&gt;"</td>
    </tr>
</table>

## Sets

Os conjuntos, representados por ``[]``, podem ter os seguintes argumentos:

<table>
    <tr>
        <td>Set</td>
        <td>Descrição</td>
    </tr>
    <tr>
        <td>[arn]</td>
        <td>Retorna a ocorrência de qualquer dos caracteres específicados (a, r, ou n)</td>
    </tr>
    <tr>
        <td>[a-z]</td>
        <td>Retorna todas as ocorrências de letras minusculas entre a e z</td>
    </tr>
    <tr>
        <td>[A-Z]</td>
        <td>Retorna todas as ocorrências de letras maiusculas entre A e Z</td>
    </tr>
    <tr>
        <td>[^a-z]</td>
        <td>Negação. Retorna todas as ocorrências, exceto as que foram específicadas</td>
    </tr>
    <tr>
        <td>[0-9]</td>
        <td>Retorna as ocorrências de 0 a 9</td>
    </tr>
    <tr>
        <td>[0-5][0-7]</td>
        <td>Retorna as ocorrências entre 00 e 57</td>
    </tr>
    <tr>
        <td>[n], n = +, *, ., |, (), $,{} </td>
        <td>Retorna a ocorrência de qualquer caracter especial específicado no conjunto</td>
    </tr>
</table>

## Sequência Especiais

Alguns conjuntos podem ser resumidos a certas sequências.

<table>
    <tr>
        <td>Character</td>
        <td>Descrição</td>
        <td>Exemplo</td>
    </tr>
    <tr>
        <td>\A</td>
        <td>Retorna se os caracteres informados estiverem no início da string</td>
        <td>r"\AOla"</td>
    </tr>
    <tr>
        <td>\Z</td>
        <td>Retorna se os caracteres informados estiverem no fim da string</td>
        <td>r"\Mundo"</td>
    </tr>
    <tr>
        <td>\b</td>
        <td>Retorna se os caracteres informados estiverem no início ou fim da palavra</td>
        <td>r"\bOl" r"ndo\b"</td>
    </tr>
    <tr>
        <td>\B</td>
        <td>Negação do \b</td>
        <td>r"\BOl" r"ndo\B"</td>
    </tr>
    <tr>
        <td>\d</td>
        <td>Equivalente a [0-9]</td>
        <td>r"\d"</td>
    </tr>
    <tr>
        <td>\D</td>
        <td>Negação do \d</td>
        <td>r"\D"</td>
    </tr>
    <tr>
        <td>\s</td>
        <td>Retorna a ocorrência onde a string tenha espaço em branco</td>
        <td>"\s"</td>
    </tr>
    <tr>
        <td>\S</td>
        <td>Negação do \s</td>
        <td>"\S"</td>
    </tr>
    <tr>
        <td>\w</td>
        <td>Equivalente a [a-zA-Z0-9À-ú_]</td>
        <td>"\w"</td>
    </tr>
    <tr>
        <td>\W</td>
        <td>Negação do \w</td>
        <td>"\W"</td>
    </tr>
    <tr>
        <td>\b</td>
        <td>Coloca "borda" na string</td>
        <td>"\b"</td>
    </tr>
</table>

## Exemplos

    #Retorna somente as palavras com 4 letras
    print(re.findall(r'\b\w{4}\b', texto))

    #Retorna o que há dentro das tags
    tags = """ <h1>Titulo 1</h1> <h2>Titulo 2</h2> <h3>Titulo 3</h3>"""
    print(re.findall(r'<[h123]{2}>(.*?)<\/[h123]{2}>', tags))

## Lookahead e Lookbehind

Lookahead -> Encontrar ocorrência com determinada palavra a frente

Lookbehind -> Encontrar ocorrência com determinada palavra atrás


    log = '''
    OFFLINE 192.168.0.1 active
    ONLINE 192.168.0.2 inative
    OFFLINE 192.168.0.3 active
    ONLINE 192.168.0.4 inative
    '''
    #normal
    print(re.findall(r'\w\s(\d+\.\d+.\d+\.\d)\s\w', log))
    ['192.168.0.1', '192.168.0.2', '192.168.0.3', '192.168.0.4']
    #Positive lookhead
    print(re.findall(r'\w\s(\d+\.\d+.\d+\.\d)\s(?=active)', log))
    ['192.168.0.1', '192.168.0.3']
    #Negative lookhead
    print(re.findall(r'\w\s(\d+\.\d+.\d+\.\d)\s(?!active)', log))
    ['192.168.0.2', '192.168.0.4']
    #Positive lookbehind
    print(re.findall(r'(?<=ONLINE)\s(\d+\.\d+.\d+\.\d)\s\w', log))
    ['192.168.0.2', '192.168.0.4']
    #Negative lookbehind
    print(re.findall(r'(?<!ONLINE)\s(\d+\.\d+.\d+\.\d)\s\w', log))
    ['192.168.0.1', '192.168.0.3']

## Referências
* [Documentação Python](https://docs.python.org/pt-br/3.8/howto/regex.html)
* [W3School](https://www.w3schools.com/python/python_regex.asp)
* [Automatize Boring Stuff](https://automatetheboringstuff.com/2e/chapter7/)