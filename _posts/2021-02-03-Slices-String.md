---
layout: post
title: Slices String
categories: python
tags: [python, strings, slices]
toc: true
---

Com python podemos acessar os caracteres de uma string pelo seu index.

## Entendendo como as strings são indexadas
Assim como uma `list` em que cada posição possui um index, os caracteres de uma string também correspondem a um index começando pelo número 0.

Para entendermos melhor, vamos analisar a string `italo marcos`

| i  | t  | a  | l  | o  |   | m  | a  | r  | c  | o  | s  |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9  | 10  | 11  |

Como podemos observar, o caractere `i` corresponde a `0`, `t` a 1, ..., o espaço também é representado e corresponde a `5`, ..., e por último, `s` corresponde a `11`

## Acessando os caracteres pelo seu index
```
name = "italo marcos"
print(name[2])
print(name[5])
print(name[9])

Output
a

o
```

## Fatiando as strings
Como o próprio nome já diz, slice, podemos fatiar as strings de acordo com os seus index.

O slice possui os seguintes parâmetros: `string[a:b:c]`. O parâmetro `a` se refere a partir de que index começará o slice (incluindo). O parâmetro `b` se refere quando o slice terminará (excluindo). O `c` se refere os passos que serão saltados.

Tudo só fica mais claro a partir de exemplos:

```
print(name[0:5])

Output
italo
```
Como observado no exemplo acima, começamos do index `0` e fomos até index `4`, pois o parâmetro `5` é o limite.

```
print(name[0:12])
print(name[0:12:1])

Output
italo marcos
italo marcos
```
Nesse exemplo percebemos o uso do terceiro parâmetro. Mas o que ele faz? Simplesmente fala para ir do index `0` ao `11` de `1` em `1`. O que acontece se mudarmos para `2`?
```
print(name[0:12:2])

Output
iaomro
```
Fatiamos a string de dois em dois.

## Omitindo os parâmetros
Se omitirmos o primeiro parâmetro, estamos falando que queremos pegar a string do começo:
```
print(name[:12:3])

Output
ilmc
``` 

Se omitirmos também o segundo parâmetro, estamos falando que queremos pegar toda a string:
```
print(name[::4])

Output
i o
``` 

## Index Negativo
E se quiséssemos pegar somente a última letra da string? Podemos utlizar o index `-1`. 
```
print(name[-1])

Output
s
```

Com a string `italo marcos`, a tabela de index negativo fica assim:

| i  | t  | a  | l  | o  |   | m  | a  | r  | c  | o  | s  |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| -12  | -11  | -10  | -9  | -8  | -7  | -6  | -5  | -4  | -3  | -2  | -1  |

Como seria para inverter a string?
```
print(name[::-1])

Output
socram olati
```

Agora que já entendemos o básico, podemos testar a vontade =D.

## Referências
* [Documentação python](https://docs.python.org/3/library/functions.html?highlight=slice#slice).
* [Digital Ocean Community](https://www.digitalocean.com/community/tutorials/how-to-index-and-slice-strings-in-python-3).


