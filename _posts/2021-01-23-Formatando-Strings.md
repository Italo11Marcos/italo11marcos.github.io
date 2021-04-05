---
layout: post
title: Formatando strings
categories: python
tags: [python, strings]
toc: true
---

Quando estamos programando, sempre se faz necessário ter um maior controle sobre a formatação da saída, ao invés de simplesmente exibir os valores da forma que eles vêm.

### Utilizando `f` ou `F`
```
resultado = 25+4
print(f'25 + 4 = {resultado}')
output: '25 + 4 = 29'
```

### Utilizando `format`
```
votos_validos = 3435323
votos_invalidos = 55544
print('{} votos válidos x {} votos inválidos'.format(votos_validos, votos_invalidos))
output: '3435323 votos validos x 55544 votos inválidos'
```

### Tambem é possível formatar as saídas utilizando diversas diretivas
```
porcentagem = votos_validos / (votos_validos + votos_invalidos)
print('Porcentagem de votos válidos: {:2.2%}'.format(porcentagem))
output: 'Porcentagem de votos válidos: 98.41%'
```

### Formatando casas decimais
```
import math
print(f'O valor aproximado de pi é {math.pi:.4f}')
output: 'O valor aproximado de pi é 3.1416'
```

### Alinhar a formatação
```
tabela = {'AAA': 111, 'BBB': 222, 'CCC': 333}
for x, y in tabela.items():
    print(f'{x:10} <--> {y:10}')
output:'AAA        <-->        111
        BBB        <-->        222
        CCC        <-->        333'
```

### Posicionar argumentos
```
print('{0} e {1}'.format('A', 'B'))
print('{1} e {0}'.format('A', 'B'))
output: 'A e B'
        'B e A'
```

### Nomear argumentos
```
print('Essa {coisa} é {adjetivo}'.format(coisa='comida', adjetivo='boa'))
output: 'Essa comida é boa'
```

Essas são apenas algumas formatações que podemos fazer, existem várias outras formas que podem ser estudadas [aqui](https://docs.python.org/pt-br/3/tutorial/inputoutput.html).

