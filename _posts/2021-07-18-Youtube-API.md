---
layout: post
title: Youtube API
categories: api
tags: [api, youtube]
toc: true
---

Utilizando a API do Youtube

A API do youtube permite recuperar dados de canais, playlists, vídeos e suas estatísticas, como número de views, likes, unlikes, total de vizualizações dentre outras coisas. Vale muito a pena ler a documentação.

Antes de começar, é necessário gerar sua ``api_key`` para podermos fazer as requisições. Para isso basta acessar o
[Google API Console](https://console.developers.google.com/) e gerar sua key. 

## Começando

Para começar, é necessário instalar a lib ``google-api-python-client``:

    pip install --upgrade google-api-python-client

A base dos scripts é sempre a mesma, vamos conferir:

    youtube = build("youtube", "v3", developerKey=api_key)

    # Primeiro criamos Youtube Resource Object
    # ``api_key`` é a sua chave

Recuperando os dados:

    response = youtube.playlists().list(
            part = "snippet",
            channelId = channel_id,
            maxResults = 50,
        ).execute()

    # Com o objeto ``youtube``, chamamos o recurso  da API e qual métodos que desejamos utilizar, nesse exemplo: playlists().list()
    # part: Esse parâmetro indica qual propriedade de recurso será incluída na resposta da API
    # O segundo parâmetro varia de acordo com o recurso, mas sempre é referente ao ID do que você deseja recuperar
    # maxResults: Esse parâmetro indica o máximo de resultados, por padrão é 5 e o máximo é 50.

O ponto comum da utilização da api do youtube são esses. A seguir, 3 exemplos de utilização:

1. [Recuperar comentários de vídeos](https://github.com/Italo11Marcos/youtubeAPI/blob/main/comments.py)
2. [Recuperar vídeos das playlists](https://github.com/Italo11Marcos/youtubeAPI/blob/main/playlists.py)
3. [Recuperar estatísticas dos vídeos](https://github.com/Italo11Marcos/youtubeAPI/blob/main/videos_playlist.py)

## Referências:
* [Github](https://github.com/Italo11Marcos/youtubeAPI)
* [Geeks for Geeks](https://www.geeksforgeeks.org/how-to-extract-youtube-comments-using-youtube-api-python/)
* [Stackoverflow](https://stackoverflow.com/questions/62347194/youtube-api-get-all-playlist-id-from-a-channel-python)
* [Programação Dinâmica](https://www.youtube.com/channel/UC70mr11REaCqgKke7DPJoLg)
