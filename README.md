# FRONT_END_EJERCICIOS_JEKYLL
* Alberto Martín Núñez

El objetivo de esta práctica es conocer como es una estrutura con Jekyll y realizar una serie de ejercicios y modificaciones para familiarizarnos con Jekyll.

## Índice de contenido
1. [Analizaremos el proyecto básico](#id1)
2. [Ejercicios realizados](#id2)

## 1. Analizaremos el proyecto básico <a name="id1"></a>

La estructura que viene predefinida en nuestro ejemplo la podemos ver en la siguiente imagen:

<img src="img/struct.png" alt="Estructura Jekyll">

Podemos destacar de esta estructura cosas nuevas como:

*- Los includes* --> Codigo html que se va a poder incluir
*- Los layouts* --> Plantillas en donde vamos a incluir los ficheros
*- Los posts* --> Donde crearemos y se almacenarán nuestros posts
*- _site* --> Tendremos todo el contenido de nuestra página 

Para familiarizarnos con Jekyl vamos a hacer dos tareas: Añadiremos dos pagina y un post adicionales al proyecto.

# Añadiendo dos paginas adicionales al proyecto

Se le ha añadido dos páginas adicionales a este proyecto con Jekyllllamadas *Contact* y *Products* de la siguiente forma:

Se han creado dos ficheros **MarkDown** con cada nombre y se ha modificado dentro del fichero el FronMatter y se ha puersto un texto en negrita para corroborar que se crea esa pagina al pinchar en ella.

*About se refleja pero about ya esta creado*

- Estructura con los ficheros markdown creados en el proyecto

<img src="img/Ficheros_md.png" alt="Estructura con los ficheros markdown nuevos">

- Contenido del fichero, en este caso de **productos**

<img src="img/Contenido_md.png" alt="Contenido de un fichero mark down de la pagina de productos">

- Elementos que se crean cuando ejecutas el server

<img src="img/Estructura_automatica.png" alt="Estructura que se crea automaticamente">

- Como quedaría en el *index.html*

<img src="img/index.png" alt="Muestra como se modifica el index.html automaticamente">


# Añadien un post al proyecto

Esta parte ya estaría hecha guardado en /sites/index.html
**Porque no se me carga la estructura de article como en el otro post**
        
Añadir si esta ok una imagen con el codigo y el servidor corriendo


## 2. Ejercicios realizados <a name="id2"></a>

# Identifica objetos, filtros y etiquetas en el siguiente fragmento de código e indica cuál es u finalidad.

```
{% assign episodes = site.episodes | sort: 'weight' %}  
        `{% for episode in episodes limit: 6 %}  
          `<div class="grid__cell grid__cell--33">
            `{% include episode_preview.html episode=episode %}
          </div>
        {% endfor %}

```

*SOLUCION:*

**PREGUNTAR MAÑANA JUEVES**

# Qué código html tendría como salida

```

<html>   
        <head>  
           <title>{{ page.title }} -Ejemplo Jekyll </title>
        </head>
        <body>  
           {% include nav.html %}` 
           {{ content }}
        </body>  
</html> 

```

*SOLUCION:*

Tendríamos en el head un titulo de la pagina con el nombre que se haya establecido en la variable title del layout con nombre **page** mas *"-Ejemplo Jekyll"*. 
En el cuerpo del html se incluye un fichero *nav.html* y posteriormente el contenido del layout por defecto.

# Especifica los filtros, variales Jekyll, tags, y qué se consigue con el siguiente código

```
<footer id="footer">
    <p class="small">© Copyright {{ site.time | date: '%Y' }} {{ site.author }}</p>
</footer>


```

*SOLUCION:*

En el codigo tenemos una etiqueta **footer** (pie de pagina). Dentro de ella hay otra etiquete **p**(párrafo) con una *clase* que se llama small y con un contenido "**© Copyright {{ site.time | date: '%Y' }} {{ site.author }}**" en donde podemos destacar las siguientes variable Jekyll:

*- site.time* devuelve la hora cuando se ejecuta Jekyll en el siguiente formato:
**2019-11-11 12:56:48 +0000**
Pero al aplicarle un filtro, `| date: '%Y'` , nos quedaríamos con el año por lo que el resultado seria : **2019**
*- site.author* devolveria el valor de la variable author que si no esta definida no tendría nada en su interior.

Por lo que el resultado del codigo anterior seria:

**© Copyright 2019**

# dicar qué scripts se están invocando con el siguiente código

```
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
  <script src="{{ "/" | relative_url  }}assets/js/main.js"></script>
  <script src="{{ "/" | relative_url  }}assets/js/highlight.js"></script>
  
```
*SOLUCION:*

# Indica el resultado que se obtiene con el siguiente código, sabiendo que paginas corresponde la colección de almacenada en _characters

```
<ul class="nav">
          {% assign paginas = site.paginas | sort: 'name' %}
          {% for pagina in paginas %}
            <li class="nav__item">
              <a href="{{ pagina.url }}">{{ pagina.title }}</a>
            </li>
          {% endfor %}
</ul>

```

*SOLUCION:*

# Dada una colección de documentos con las siguientes variables en el frontmatter
```
title: Mi Pagina
thumbnail_url:  https://XXX
image_url: https://

```
Indicar que objetivon tiene el siguiente include:

```
<a href="{{ character.url }}" class="character-preview">
  <img src="{{ character.thumbnail_url }}" class="character-preview__image" />
  <div class="character-preview__label">
    {{ character.title }}
  </div>
</a>

```

*SOLUCION:

