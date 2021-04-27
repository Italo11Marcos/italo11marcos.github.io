---
layout: post
title: Boas práticas com python - PEP8
categories: python
tags: [python, PEP8]
toc: true
---

PEP 8, PEP8 ou PEP-8 é documento sobre boas práticas de como escrever um código legível em python.

Ter um código legível é essencial, pois passamos mais tempo lendo e estudando códigos que escrevendo. Muitas vezes lemos o código cinco, seis vezes para corrigirmos somente uma linha. Muitas vezes também, seu código vai ser lido por diversas outras pessoas, e para facilitar o entendimento do mesmo é essencial manter o código legível. Veremos a seguir algumas dicas.

# Nomes de varíaveis
Quando começamos a programar, gostamos muito de criar variáveis com letras simples, como "x, y, z", para pouparmos tempo digitando, no entanto, se fizermos isso em um projeto maior, ficará bem confuso.

    #Não use l, O ou i como nomes de variávels, pois dependendo da fonte, poderá ser confundido por 0, 1. 
    O = 1 #Aqui pode ficar parecendo que você está passando o valor de 2 para zero
    l = 2 #Aqui pode confundir a letra 'l' (ascii code 108), com o número '1' (ascii code 49) ou com a letra 'i' (ascii code 105)

    #Use sempre nomes que lembre diretamento o que a variável representa.
    x = 'Italo Marcos" #Errado
    name = 'Italo Marcos #Certo

| Type     | Descrição                                                                                           | Exemplos                |
|----------|-----------------------------------------------------------------------------------------------------|-------------------------|
| Function | Use palavras com letras minúsculas e separe com '_' (ascii code 95). Padrão snake_case              | function, my_function   |
| Variable | Use palavras com letras minúsculas e separe com '_' (ascii code 95). Padrão snake_case              | variable, my_variable   |
| Class    | Use palavras com a primeira letra sempre maiúscula. Não use nada para separa-las. Padrão PascalCase | MyClass, MyClassOne     |
| Method   | Use palavras com letras minúsculas e separe com '_' (ascii code 95). Padrão snake_case              | my_method, method       |
| Constant | Use sempre letras maiúsculas e separe com '_' (ascii code 95)                                       | CONTANT, MY_CONSTANT    |
| Module   | Use palavras com letras minúsculas e separe com '_' (ascii code 95). Padrão snake_case              | my_module.py, module.py |
| Package  | Use palavras com letras minúsculas. Não use nada para separá-las.                                   | mypackage, package      |


# Espaços
Outra dúvida que sempre temos na hora de escrever o código é como devemos separar as classes, funções, quantos "espaços" devemos utilizar. 

A PEP8 fala que devemos utilizar "dois espaços em branco" para classes e funções:
    
    class MyClass:
        pass


    def my_function():
        pass

Para os métodos de dentro das classes, é recomendado deixar somente um "espaço":

    class MyClass:
        def first_method(self):
            pass

        def second_method(self):
            pass

Quando uma função for muito grande, é recomendado deixar um "espaço" para cada passo:

    def calculate_variance(number_list):
        sum_list = 0
        for number in number_list:
            sum_list = sum_list + number
        mean = sum_list / len(number_list)

        sum_squares = 0
        for number in number_list:
            sum_squares = sum_squares + number**2
        mean_squares = sum_squares / len(number_list)

        return mean_squares - mean**2


# Quebra de linha
Outro problema comum que passamos é quando passamos muito paramêtros ou importamos muitas funções e as linhas ficam gigantes.

A PEP8 recomenda a quebra de linha para não ficar muito extenso:

    #Se for argumentos das funções, use ',' para quebrar a linha
    def function(arg_one, arg_two,
             arg_three, arg_four):
        return arg_one

    #Quando for 'import', use a 'barra invertida' para quebrar a linha
    from mypackage import example1, \
        example2, example3

    #Quando tiver operadores binários como '+, -, *', quebre as linhas com o operador sempre no lado esquerdo
    total = (variable_one 
             + variable_two
             - variable_three)


# Espaços em expressões matemáticas
Também costumamos escrever expressões matemáticas quando estamos programando, a sempre bate aquela dúvida se devemos deixar espaços ou não nas expressões.

A PEP 8 recomenda tirar os 'espaços' nas expressões:

    #Certo
    x = (a+b) * (c-d)
    if x>y and x%2 == 1:

    #Errado
    x = (a + b) * (c - d)
    if x > y and x % 2 == 1:

# Comparações com True e False
É normal fazermos comparações se alguma variável é ``True`` ou ``False``. Mas não devemos comparar valores booleanos usando ``==``.

    #Certo
    if variable:
    #Errado
    if variable == True:

Vários desses exemplos eu peguei do ótimo site RealPython. Link mais embaixo.

Essas foram somente algumas recomendações que eu achei mais pertinentes, o que costumamos fazer mais. Para mais informações acesse a documentação oficial.

* [PEP8](https://www.python.org/dev/peps/pep-0008/)
* [RealPython](https://realpython.com/python-pep8/)

