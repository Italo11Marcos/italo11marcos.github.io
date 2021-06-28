---
layout: post
title: Comandos básicos Git
categories: git
tags: [git]
toc: true
---

Alguns comandos básicos do git

## Criar branch

    git checkout -b <branchname>

ou

    git switch -c <branchname>

## Trocar branch

    git checkout <branchname>

ou

    git switch <branchname>

## Juntar branch

    git merge <branchname>

## Juntar commits

    git rebase -i HEAD~X
    
    HEAD -> significa que está no trabalho atual
    X -> quantos commits deve juntar

## Restaura um commit

    git restore

    Esse comando restaura o ambiente de trabalho, descartando os commits que não são mais necessários

## Desfazer mudanças não commitadas

    git checkout --<file>

    É como se fosse ctrl+z

## Desfazer commits quando estão como stagged

    git reset HEAD <file>

## Desfazer commit

    git log (copia a hash)

    git revert <hash>

## Ver a diferença entre os commits

    git diff <hash>..<hash>

## Criar tag - cria uma versão do projeto

    git tag -a nome

    git push origin master <tag>

## Guardar para depois

    git stash               ->salva as alterações

    git stash list          ->lista do que está guardado

    git stash apply index   ->aplica as alterações

    git stash drop          ->remove da lista

    git stash pop           ->aplica e remove da lista

## Referências

* [Documentação GIT](https://git-scm.com/)