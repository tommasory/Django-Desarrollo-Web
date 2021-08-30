# Creación del Blog - Fundamentos de django y desarrollo web

En este curso creamos una agina web desde cero, además en este curo se maneja la metodología Git Flow, este curse se centrara en crear un blog dinámico en el cual se podrá crear, borrar contenido y usar imágenes, en este blog se va poder crear usuarios, además tendrá una sección de administradores y los post del blog van a poder tener likes, comentarios y poder mirar la cantidad de vistas. 

## theory study

* **Llamando objetos**

Llamar a todos los objetos
```sh
Entry.objects.all()
```
Filtro de objetos por atributo
```sh
Entry.objects.filter(name='new name')
```
Filtrar los primeros registros
```sh
Entry.objects.first()
```
Filtrar por atributo **DateField()**, filtro por año, mes, dia.
```sh
Entry.objects.filter(nombre_atributo__year=2020)
Entry.objects.filter(nombre_atributo__month=3)
```
Filtrar por atributo **IntegerField()**.
* Mayor o igual a 5
* Menor o igual a 5
* Exactamente 5
```sh
Entry.objects.filter(nombre_atributo__gte=5)
Entry.objects.filter(nombre_atributo__lte=5)
Entry.objects.filter(nombre_atributo=5)
```
Filtrar por atributo **CharField()**.
* Si el campo empiza con una palabra
```sh
Entry.objects.filter(nombre_atributo__startswitch='new')
```
Encadenamineto de filtros
* Filtro de caracteres
* Filtro de exclusión
* Filtro de enteros
```sh
Entry.objects.filter(nombre_atributo__startswitch='new').exclude(nombre_atributo__year=2020).filter(nombre_atributo=7)
```

* **Mas lookups**

Buscar un objeto que sabemos que existe
```sh
Entry.objects.get(attribute_name='tomas')
```
Limitar lista de busqueda
* Las 100 primeras
```sh
Entry.objects.all()[:100]
```

* **Lookup en mayusculas**

Buscar un objeto exacto
* Le importa la mayuscula por eso no encuntra nada
```sh
Entry.objects.filter(attribute_name__exact='tomaS')
```
Buscar un objeto inexacto
* No le importa la mayuscula igual lo busca
```sh
Entry.objects.filter(attribute_name__inexact='tomaS')
```
Buscar un objeto que en su campo **CharField()**, contenga una palabra exactamente.
* No retornar nada porque busca **tomas**
```sh
Entry.objects.filter(attribute_name__contains='tomaS')
```
Buscar un objeto que en su campo **CharField()**, contenga una palabra exactamente.
* Retornar porque busca **tomas**, sin importar si tiene mayusculas.
```sh
Entry.objects.filter(attribute_name__incontains='tomaS')
```

* **Span lookups**


* **Caching**


* **Q lookups**


* **Objetos relacionados**

