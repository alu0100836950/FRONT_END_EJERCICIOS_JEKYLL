# FRONT_END_EJERCICIOS_JEKYLL
* Alberto Martín Núñez

El objetivo de esta práctica es conocer como es una estrutura con Jekyll y realiza runa serie de ejercicios y modificaciones para familiarizarnos con el Jekyll.

## Índice de contenido
1. [Analizaremos el proyecto básico](#id1)
2. [Ejercicios realizados](#id2)

## 1. Analizaremos el proyecto básico <a name="id1"></a>
Poner estructura de ficheros de Jekyll y definir mas o menos como es la estructura que se usa con Jekyll
# Añadir dos paginas adicionales al proyecto

# Añadir un post al proyecto
Esta parte ya estaría hecha guardado en /sites/index.html
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

