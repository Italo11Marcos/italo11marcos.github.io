---
layout: post
title: Import data from CSV to Database
categories: python
tags: [python, csv, database]
toc: true
---

Importando dados de um arquivo csv para banco de dados.

As vezes é necessário importar grande volume de dados de um arquivo para o banco de dados. 

O ``Django`` possui um método chamado [``bulk_create``](https://docs.djangoproject.com/en/3.0/ref/models/querysets/#bulk-create) que facilita e agiliza muito o processo, pois gera somente 1 query, não importando quantos objetos a serem inseridos.

O script pode ser encontrado [aqui](https://github.com/Italo11Marcos/import_data_from_csv/blob/main/import_data.py) junto a um exemplo com o django acessando [aqui](https://github.com/Italo11Marcos/import_data_from_csv).

    import os
    import csv
    import django

    #Troque o "library" pelo nome do seu projeto
    if __name__ == "__main__":
        try:
            os.environ.setdefault("DJANGO_SETTINGS_MODULE", "library.settings")
            django.setup()
        except ImportError:
            raise ImportError(
                "Não foi possível importar o Django.\n"
                "Verifique se o seu virtual environment está ativado.\n"
                "Verifique se está no mesma pasta do projeto.\n"
                "Verifique se o nome do seu projeto está correto.\n"
            )

        #Importe os seus models
        from books.models import Book
        
        #Apaga todos os registros
        Book.objects.all().delete()

        books = []
        with open('books_library.csv', encoding='utf8') as csvfile:
            rows = csv.DictReader(csvfile)
            for row in rows:
                book = Book(id=row['book_id'], title=row['title'], 
                            author=row['author'], isbn13=row['isbn13'], 
                            avg_rating=row['avg_rating'], publisher=row['publisher'], 
                            pages=row['pages'], year_published=row['year'])
                books.append(book)

        Book.objects.bulk_create(books)
