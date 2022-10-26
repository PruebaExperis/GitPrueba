***Sobre este documento***

  He   escrito este documento para ayudar a las personas dedicadas al mundo de la informática a entender y familiarizarse los con conceptos del lenguaje markdown.  

Para escribirlo he utilizado la propia sintaxis de markdown (asegurándome de incluir todos y cada uno de los recursos que nos brinda este lenguaje para maquetar documentos) de forma que pueda ser a su vez utilizado como una plantilla en la que consultar cómo conseguir un determinado resultado.

La última versión de este documento puede encontrarse en:
> <https://gitlab.iochannel.tech/markdown/README.md>

Este documento está sujeto a cambios, y agradezco tu colaboración. Puedes enviarme cualquier comentario o sugerencia con respecto a este documento a:
> Iván Osuna: <ivan@iochannel.tech>

Este archivo está bajo una licencia:
> [Creative Commons Atribución-SinDerivadas 4.0 Internacional](http://creativecommons.org/licenses/by-nd/4.0/) ![Licencia Creative Commons](https://i.creativecommons.org/l/by-nd/4.0/80x15.png)

***Convenciones***

Algunas características que he expuesto en este documento no están disponibles en la especificación original de markdown, y solamente funcionan en las especificaciones extendidas implementadas en github y/o gitlab. 

Por este motivo, he identificado con los iconos: <img src="github.svg" alt="github" height="20pt" /> y <img src="gitlab.svg" alt="gitlab" height="20pt" /> respectivamente aquellas características que sólo están disponibles en estas herramientas.

Adicionalmente he utilizado:
- El icono 💡&nbsp;para identificar consejos o trucos que me han sido útiles a la hora de escribir documentos en formato markdown.
- El icono ⚠️&nbsp;para identificar problemas o dificultades con las que me he encontrado al usar ciertas características de markdown.

---

# El lenguaje markdown

1. [Introducción a markdown](#introducción-a-markdown)
1. [Uso de markdown en git](#uso-de-markdown-en-git)
1. [TL; DR](#tl-dr)
1. [Estilos y elementos dentro de un texto](#estilos-y-elementos-dentro-de-un-texto)
    - [Cursiva](#cursiva)
    - [Negrita](#negrita)
    - [Negrita y cursiva](#negrita-y-cursiva)
    - [Tachado](#tachado)
    - [Código](#código)
    - [Salto de línea](#salto-de-línea)
    - [Enlaces](#enlaces)
    - [Enlaces referenciados](#enlaces-referenciados)
    - [Notas al margen](#notas-al-margen--)
    - [Imágenes](#imágenes)
1. [Estilos de párrafos](#estilos-de-párrafos)
    - [Párrafos normales](#párrafos-normales)
    - [Títulos](#títulos)
    - [Listas](#listas)
        - [Listas no numeradas](#listas-no-numeradas)
        - [Listas numeradas](#listas-numeradas)
        - [Sublistas](#sublistas)
        - [Listas de tareas](#listas-de-tareas--)
1. [Formatos especiales de bloque](#formatos-especiales-de-bloque)
    - [Línea de separación](#línea-de-separación)
    - [Cita](#citas)
    - [Código](#código)
1. [Tablas](#tablas)

---

## Introducción a markdown

La sintaxis **markdown** permite *maquetar* [^1] un documento mediante el uso de unas ___marcas___ y unas ___reglas sintácticas___ muy simples.

Aunque no se utiliza sólo para ello, markdown es el formato estándar para documentar y dar información en los repositorios git, y es interpretado automáticamente por los principales servicios cloud de git, como:
- [github](https://github.com)
- [gitlab](https://gitlab.svg)
- [bitbucket](https://bitbucket.org)

Otros usos habituales de markdown son:
- [La documentación de charts de Helm para Kubernetes](https://helm.readthedocs.io/en/latest/awesome/#the-readmemd-file)
- [La documentación de roles de Ansible](https://docs.ansible.com/ansible/latest/galaxy/dev_guide.html)
- La documentación de imágenes de Docker en hub.docker.com

A los archivos escritos según la sintaxis markdown les añadimos la extensión `.md`.

El icono habitual que utilizamos para representar archivos markdown es:

![Icono archivo markdown](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/312px-Markdown-mark.svg.png "Icono estandar de un archivo markdown")

La sintaxis de markdown fue creada en el año 2004 por John Gruber, con ayuda de Aaron Swartz. La página oficial donde se detalla su especificación del lenguaje es: <https://daringfireball.net/projects/markdown/>.

Más adelante han ido surgiendo implementaciones de markdown que permiten utilizar características adicionales. Entre ellas destacan:
- [Github flavoured markdown](https://github.github.com/gfm/)
- [Gitlab flavoured markdown](https://docs.gitlab.com/ee/user/markdown.html)

## Uso de markdown en git 

Como hemos explicado en la [introducción](#introducción-a-markdown), los principales servicios de git en cloud buscan en cada carpeta un archivo llamado `README.md`. 
Si el archivo existe, automáticamente lo convierten a HTML aplicando unas reglas de maquetado que facilitan su lectura por personas y lo muestran por pantalla.

Los desarrolladores que colocan su código en un sistema de control de versión git, utilizan estos archivos para ayudar a entender el contenido de una determinada carpeta o repositorio al resto de personas interesadas en el proyecto.

## TL; DR

En esta tabla resumo la mayor parte de símbolos utilizados en markdown, su significado dentro de este lenguaje y ejemplos de uso. 

> En apartados posteriores detallo algunos aspectos adicionales, así como buenas prácticas al respecto de su utilización:

### Estilos y elementos dentro de textos:

| Formato | Símbolo | Ejemplo | Disponible en |
| ------- | :-----: | ------- | ---: |
| [Cursiva](#cursiva) | ```*```<br>```_``` | ```*esto sale en cursiva*```<br>```_esto también_``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Negrita](#negrita) | ```**```<br>```__``` | ```**esto sale en negrita**```<br>```__``` ```esto también__``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Negrita y cursiva](#negrita-y-cursiva) |  ```***```<br>```___```  | ```***esto sale en negrita y cursiva***```<br>```___esto también___```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Tachado](#tachado) | ```~~```| ```~~esto sale tachado~~```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Código](#código) | `` ` ``| `` `esto sale como código` `` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Salto de línea](#salto-de-línea) | ```<br>```| ```Esto es una línea<br>Esto sería otra línea``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Enlace sencillo](#enlaces) | ```<>``` | ```<https://iochannel.tech>``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Enlace personalizado ](#enlaces) | ```[texto a mostrar](url)``` | ```[Web de IOChannel](https://iochannel.tech)``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Enlace que abre en nueva pestaña](#enlaces) | ```[texto a mostrar](url){:target="_blank"}``` | ```[Web de IOChannel](https://iochannel.tech){:target="_blank"}``` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Enlace a título del mismo documento](#enlaces) <br> | ```[texto a mostrar](#url)``` | ```[Introducción](#introduccion-del-documento)``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Imagen](#imágenes) | ```[alt](url)``` | ```[Logo de IOChannel]```\(https://iochannel.tech/logo) | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Imagen con título](#imágenes) | ```[alt](url título)``` | ```[Logo de IOChannel]```(https://iochannel.tech/logo) ```"Logotipo de IOChannel" )``` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Referencia a nota al margen](#notas-al-margen--) | ```[^1]``` | ```véase nota [^1]``` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |

### Formatos de Título:

| Formato | Símbolo | Ejemplo | Disponible en |
| ------- | :-----: | ------- | ---: |
| [Encabezado principal <br> Título 1](#títulos) | ```#``` | ```# Esto sería un título```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Encabezado secundario <br> Título 2](#títulos) | ```##``` | ```## Esto sería un subtítulo```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Título de nivel 3](#títulos) | ```###``` | ```### Esto sería un apartado ```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Título de nivel 4](#títulos) | ```####``` | ```#### Esto sería un subapartado``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Título de nivel 5](#títulos) | ```#####``` | ```##### Esto sería una sección``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Título de nivel 6](#títulos) | ```######``` | ```###### Esto sería una subsección``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |

### Formatos de listas:

| Formato | Símbolo | Ejemplo | Disponible en |
| ------- | :----- | ------- | ---: |
| [Lista](#listas) | ```-```<br>```*```<br>```+``` |  ```- Esto es una lista```<br> ```- Con varios elementos```<br> &nbsp;&nbsp;&nbsp;&nbsp;```* Esto sería una sublista```<br> &nbsp;&nbsp;&nbsp;&nbsp;```* Con varios elementos``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Lista numerada](#listas-numeradas) | ```1.```<br>```2.```<br>```3.``` | ```1. Esto es el primer elemento```<br>```2. Esto es el segundo elemento ```| <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Lista de tareas](#listas-de-tareas--) | ```- []```<br>```- [x]``` | \- ```[x] Esta es una tarea realizada```<br>\- ```[ ] Esta es una tarea sin realizar``` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |

### Formatos especiales de bloque:
| Formato | Símbolo | Ejemplo | Disponible en |
| ------- | :----- | ------- | ---: |
| [Línea de separación](#línea-de-separación) | ```---```<br>```***``` | ```---``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Cita](#citas) | ```>``` | ```> Esto aparecería como una cita.```<br><br>```> Que podría tener varias líneas```<br>```> y su **propio formato**``` | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Código](#código) |  ` ```formato`<br>`CONTENIDO`<br>` ``` ` | ` ```bash`<br>`echo HOLA`<br>` ``` ` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| [Nota al margen](#notas-al-margen--) | ```[^]:``` | ```[^1]: Esto es una nota al margen``` | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |

### Tablas (disponible en <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/>)

#### ***Ejemplo:***

```md
| Columna 1 | Columna 2 | Columna 3 | Columna 4 |
| --- | :--- | :---: | ---: |
| Alineada a la izquierda | A la izquierda | Centrada | A la derecha |
| Alineada a la izquierda | A a la izquierda | Centrada | A la derecha |
```

#### ***Resultado al visualizarse:***

| Columna 1 | Columna 2 | Columna 3 | Columna 4 |
| --- | :--- | :---: | ---: |
| Alineada a la izquierda | A la izquierda | Centrada | A la derecha |
| Alineada a la izquierda | A a la izquierda | Centrada | A la derecha |

---
## Estilos y elementos dentro de un texto

Dentro de una línea de texto, pueden aplicarme numerosos estilos a las palabras que aparecen, así como incrustar elementos adicionales como enlaces o imágenes.

Las reglas definidas en este apartado pueden utilizarse en:
- Párrafos normales
- Items de listas
- Celdas de tablas
- Bloques de citas
- Títulos

Estos son los estilos y elementos que pueden incluirse dentro de un texto:
- [Cursiva](#cursiva)
- [Negrita](#negrita)
- [Negrita y cursiva](#negrita-y-cursiva)
- [Tachado](#tachado)
- [Código](#código)
- [Salto de línea](#salto-de-línea)
- [Enlaces](#enlaces)
- [Enlaces referenciados](#enlaces-referenciados)
- [Notas al margen](#notas-al-margen--)
- [Imágenes](#imágenes)

---

### Cursiva

Utilizamos un carácter asterisco `*` o guion bajo `_` por delante y por detrás de un texto que queramos representar en cursiva.

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta *palabra* se muestra en cursiva``` | Esta *palabra* se muestra en cursiva |
| ```Esta _palabra_ también``` | Esta _palabra_ también |


#### ***Cuidado:***
- ⚠️&nbsp;Para evitar problemas con los guiones bajos en medio de una palabra, es aconsejable utilizar asteriscos en lugar de guiones bajos.

#### ***Trucos:***
- 💡&nbsp;Si queremos escribir un texto que incluya guiones bajos o que comience y acabe con guines bajos, para evitar que se muestre en cursiva y sin los guiones bajos basta con escapar el primer guion bajo con una contrabarra ```\```.

    | ***Ejemplo:*** | ***Resultado al visualizarse:*** |
    | --- | --- |
    | ```Esto: '_null_' se muestra en cursiva y sin los guiones bajos``` | Esto: '_null_' se muestra en cursiva y sin los guiones bajos |
    | ```En cambio, esto: '\_null_' se muestra con los guiones bajos y sin cursiva``` | En cambio, esto: '\_null_' se muestra con los guiones bajos y sin cursiva |

---

### Negrita

Utilizamos dos caracteres asterisco `**` o guion bajo `__` por delante y por detrás de un texto que queramos representar en negrita.

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta **palabra** se muestra en negrita``` | Esta **palabra** se muestra en negrita |
| ```Esta __palabra__ también``` | Esta __palabra__ también |

#### ***Cuidado:***

- ⚠️&nbsp;Para evitar problemas con los guiones bajos en medio de una palabra, es aconsejable utilizar asteriscos en lugar de guiones bajos.

#### ***Trucos:***

- 💡&nbsp;Si queremos escribir un texto que incluya 2 guiones bajos o que comience y acabe con 2 guiones bajos, para evitar que se muestre en negrita y sin los guiones bajos basta con escapar los dos primeros guiones bajos con una contrabarra ```\```.

    | ***Ejemplo:*** | ***Resultado al visualizarse:*** |
    | --- | --- |
    | ```Esto: '__null__' se muestra en negrita y sin los guiones bajos``` | Esto: '__null__' se muestra en negrita y sin los guiones bajos |
    | ```En cambio, esto: '\_\_null__' se muestra con los guiones bajos y sin negrita``` | En cambio, esto: '\_\_null__' se muestra con los guiones bajos y sin negrita |

---

### Negrita y cursiva

Utilizamos tres caracteres asterisco `***` o guion bajo `___` por delante y por detrás de un texto que queramos representar en negrita y cursiva simultáneamente.

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta ***palabra*** se muestra en negrita y cursiva``` | Esta ***palabra*** se muestra en negrita y cursiva |
| ```Esta ___palabra___ también``` | Esta ___palabra___ también |

#### ***Cuidado:***

- ⚠️&nbsp;Para evitar problemas con los guiones bajos en medio de una palabra, es aconsejable utilizar asteriscos en lugar de guiones bajos.

#### ***Trucos:***

- 💡&nbsp;Si queremos escribir un texto que incluya 3 guiones bajos o que comience y acabe con 3 guiones bajos, para evitar que se muestre en negrita, cursiva y sin los guiones bajos basta con escapar los tres primeros guiones bajos con una contrabarra ```\```.


    | ***Ejemplo:*** | ***Resultado al visualizarse:*** |
    | --- | --- |
    | ```Esto: '___null___' se muestra en negrita, cursiva y sin los guiones bajos``` | Esto: '___null___' se muestra en negrita, cursiva y sin los guiones bajos |
    | ```En cambio, esto: '\_\_\_null___' se muestra con los guiones bajos y sin negrita ni cursiva``` | En cambio, esto: '\_\_\_null___' se muestra con los guiones bajos y sin negrita ni cursiva |

---

### Código en medio de un texto

Utilizamos un carácter contra-comilla (también denominado acento agudo) `` ` `` por delante y por detrás de un texto que queramos representar como código dentro de un párrafo.


| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta `palabra` se muestra como código``` | Esta `palabra` se muestra como código  |

#### ***Trucos:***
- 💡&nbsp;Si queremos escribir un texto que incluya una contra-comilla, para evitar que se interprete como código utilizaremos dos contracomillas para enmarcar el texto a mostrar.

    
    | ***Ejemplo:*** | ***Resultado al visualizarse:*** |
    | --- | --- |
    | ``` `Este código incluye  `contracomillas` que deben mostrarse`.``` | `Este código incluye  `contracomillas` que deben mostrarse`. ❌ |
    | ``` ``Este código incluye  `contracomillas` que deben mostrarse``.``` | ``Este código incluye  `contracomillas` que deben mostrarse``. ✅ |
    
---

### Tachado

Utilizamos dos caracteres virgulilla `~~` por delante y por detrás de un texto que queramos representar tachado.

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta ~~palabra~~ se muestra tachada``` | Esta ~~palabra~~ se muestra tachada |

---

### Salto de línea

Para añadir un salto de línea dentro de un párrafo se utilizar el texto `<br>`.

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- | --- |
| ```Esta es una frase. <br> Y esta otra dentro del mismo párrafo``` | Esta es una frase. <br> Y esta otra dentro del mismo párrafo |

---

### Enlaces

Para añadir un enlace se pueden utilizar varias sintaxis:


| ***Ejemplo:*** | ***Código:*** | ***Resultado al visualizarse:*** | ***Uso*** |
| --- | --- |--- | --: |
| Dirección de email | ```[ivan@iochannel.tech](mailto:ivan@iochannel.tech)``` | <ivan@iochannel.tech> | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| Dirección de email  | ```<ivan@iochannel.tech>``` | <ivan@iochannel.tech> | <img src="github.svg" height="15pt"/>  <img src="gitlab.svg" height="15pt"/> |
| Enlace sencillo | ```https://iochannel.tech``` | https://iochannel.tech | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| Enlace sencillo | ```<https://iochannel.tech>``` | <https://iochannel.tech> | <img src="github.svg" height="15pt"/> <img src="gitlab.svg" height="15pt"/> |
| Enlace con texto personalizado | ```[Web de IOChannel](https://iochannel.tech)``` | [Web de IOChannel](https://iochannel.tech) | <img src="markdown.svg" height="15pt"/> <img src="github.svg" height="15pt"/>  <img src="gitlab.svg" height="15pt"/> |
| Enlace que abre en nueva pestaña | ```[Web de IOChannel](https://iochannel.tech){:target="_blank"}``` | [Web de IOChannel](https://iochannel.tech){:target="_blank"} | <img src="gitlab.svg" height="15pt"/> |


#### ***Trucos:***

- 💡&nbsp;Para aplicar formato a un enlace basta con añadirle alrededor las marcas pertinentes englobando todo el enlace o solamente el texto que se visualiza en pantalla
    
    | ***Ejemplo:*** | ***Código:*** | ***Resultado al visualizarse:*** |
    | --- | --- |--- |
    | Enlace con texto personalizado en cursiva | ```*[Web de IOChannel](https://iochannel.tech)*``` |  *[Web de IOChannel](https://iochannel.tech)*  |
    | Enlace con texto personalizado en negrita | ```[**Web de IOChannel**](https://iochannel.tech)*``` | [**Web de IOChannel**](https://iochannel.tech) |

---

### Enlaces referenciados

En ocasiones para facilitar la lectura del código markdown, usamos enlaces referenciados. 

En ellos definimos la url del enlace en un sitio del documento (normalmente al final del mismo), y podemos referenciar ese enlace a través de un identificador. Esto es especialmente útil para URLs largas.

Además, también nos evita tener que reescribir una URL que vamos a utilizar en varios lugares, lo cual favorece adicionalmente el mantenimiento del documento en caso de que la URL cambie en un futuro.

#### ***Ejemplo:***

```md
En medio de este párrafo referencio a un [enlace][web-iochannel]. La url la defino dentro del mismo documento, pero más adelante.

En medio de este párrafo también referencio a la [web de IO Channel][web-iochannel]. Se utilizará la misma URL que en el párrafo anterior.

[web-iochannel]: http://iochannel.tech "Este mensaje se mostrará en el tooltip (título del enlace)"

La línea anterior no se mostrará al formatear el documento. Simplemente la hemos utilizado para definir la URL y evitar tener que escribirla en medio del párrafo, lo que nos permite reutilizarla y facilitar la lectura del mismo.
```

#### ***Resultado al visualizarse:***

> En medio de este párrafo referencio a un [enlace][web-iochannel]. La url la defino dentro del mismo documento, pero más adelante.
> 
> En medio de este párrafo también referencio a la [web de IO Channel][web-iochannel]. Se utilizará la misma URL que en el párrafo anterior.
> 
> [web-iochannel]: http://iochannel.tech "Este mensaje se mostrará en el tooltip (título del enlace)"
> 
> La línea anterior no se mostrará al formatear el documento. Simplemente la hemos utilizado para definir la URL y evitar tener que escribirla en medio del párrafo, lo que nos permite reutilizarla y facilitar la lectura del mismo.

---

### Notas al margen <img src="github.svg" alt="github" height="20pt" /> <img src="gitlab.svg" alt="gitlab" height="20pt" />

Para añadir una nota al margen, por un lado, definimos el texto de la nota en el lugar del documento donde queremos que se muestre al maquetarlo. Para ello utilizaremos la siguiente sintaxis:

```md 
[^NUMERO DE NOTA]: Texto de la nota
```

Por otro lado, cuando queramos referenciar a la nota, simplemente utilizaremos `[^NUMERO DE NOTA]` dentro del párrafo donde queramos referenciar la nota:

#### ***Ejemplo:***

```md 
Este es el texto de un párrafo [^2], donde se referencia a una nota al margen.

Por aquí podría haber otro párrafo, tablas, imágenes y mucho otro contenido.

[^2]: Este texto es la nota al margen que se ha vinculado desde el párrafo anterior.
```

#### ***Resultado al visualizarse:***

> Este es el texto de un párrafo [^2], donde se referencia a una nota al margen.
> 
> Por aquí podría haber otro párrafo, tablas, imágenes y mucho otro contenido.
>
> [^2]: Este texto es la nota al margen que se ha vinculado desde el párrafo anterior.

Nótese que la nota al margen de este ejemplo aparecerá al final del documento.

---

### Imágenes

Para añadir una imagen utilizamos la siguiente sintaxis:

```md
![texto alternativo](url de la imagen "tooltip opcional")
```

| ***Ejemplo:*** | ***Resultado al visualizarse:*** |
| --- |--- |
| ```![Icono archivo markdown](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/312px-Markdown-mark.svg.png "Icono estándar de un archivo markdown")``` | ![Icono archivo markdown](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/312px-Markdown-mark.svg.png "Icono estandar de un archivo markdown") |

---
## Estilos de párrafos:

- [Párrafos normales](#párrafos-normales)
- [Títulos](#títulos)
- [Listas](#listas)
    - [Listas no numeradas](#listas-no-numeradas)
    - [Listas numeradas](#listas-numeradas)
    - [Sublistas](#sublistas)
    - [Listas de tareas](#listas-de-tareas--)

---
### Párrafos normales

Para escribir un párrafo normal, basta con escribir una línea de texto tal cual.

Dos líneas consecutivas se unirán mediante un espacio en blanco para dar lugar a un único párrafo al ser maquetado el documento.

Para que dos líneas sean maquetadas como párrafos independientes, debe dejarse una línea en blanco entre ellas.

#### ***Ejemplo:***

```md
Esto sería un párrafo.

Esto es una frase de un párrafo.
Esto sería considerado otra frase del mismo párrafo que la línea anterior. 
Y esta otra frase más. Estas frases se separarán entre sí mediante un espacio en blanco al ser maquetadas.

Por contra, al haber respetado una línea en blanco justo encima de esta línea, esto se mostrará como un nuevo párrafo.
```

#### ***Resultado al visualizarse:***

> Esto sería un párrafo.
> 
> Esto es una frase de un párrafo.
> Esto sería considerado otra frase del mismo párrafo que la línea anterior. 
> Y esta otra frase más. Estas frases se separarán entre sí mediante un espacio en blanco al ser maquetadas.
> 
> Por contra, al haber respetado una línea en blanco justo encima de esta línea, esto se mostrará como un nuevo párrafo.

---

### Títulos

Utilizamos el carácter `#` al principio de una línea para identificarla como un título.

El número de caracteres `#` que se utilicen, denota el nivel del título. De esta forma:
- Una única almohadilla `#` establece un título de nivel 1. El más importante.
- Dos almohadillas `##` establecen un subtítulo o título de nivel 2.
- Tres almohadillas `###` establecen un título de nivel 3.
- Así sucesivamente hasta los títulos de nivel 6, identificados por 6 almohadillas: `######`

#### ***Ejemplos:***

```md    
### Este es un título de nivel 3
#### Y este uno de nivel 4
```

#### ***Resultado al visualizarse:***

>    ### Este es un título de nivel 3
>    #### Y este uno de nivel 4


#### ***Cuidado:***

- ⚠️&nbsp;Es aconsejable dejar una línea en blanco antes y después de un título.
    ```md
    Si aquí hay un texto...    
    ### Este título no debería empezar aquí. ❌
    Ni este texto aquí debajo. ❌

    ### Este título si está bien escrito pues le precede una línea en blanco y le sigue otra línea en blanco. ✅ 
    
    Este sería el primer párrafo dentro del apartado. ✅

    ```
- ⚠️&nbsp;Es obligatorio dejar un espacio en blanco después del último carácter almohadilla.
    ```md    
    ### Este título sigue unas buenas prácticas. ✅

    ###Este no las sigue. Esto puede no ser reconocido como un título por algunos procesadores de markdown. ❌
    ```

#### ***Trucos:***

- 💡 <img src="github.svg" alt="github" height="20pt" /> <img src="gitlab.svg" alt="gitlab" height="20pt" /> Algunos procesadores de markdown (como los que se utilizan dentro de github o gitlab), generan identificadores automáticamente para cada título. El identificador tiene por valor el texto del título en minúsculas y con los espacios en blanco transformados a guiones.

    ***Ejemplo***
    
    ```md
    ### Ejemplo de título

    El título de arriba puede referenciarse mediante el enlace: 
    [Ir al apartado Ejemplo de título](#ejemplo-de-título)
    ```

    ***Resultado al visualizarse***

    >    ### Ejemplo de título
    >
    >    El título de arriba puede referenciarse mediante el enlace: 
    >    [Ir al apartado Ejemplo de título](#ejemplo-de-título)

- 💡&nbsp;Si estamos creando un archivo md que vaya a renderizarse automáticamente dentro de una página web (por ejemplo, un archivo README.md en github o gitlab), hay que tener cuidado al utilizar un título de nivel 1, ya que al procesarse dará lugar a un elemento HTML de tipo `<h1>`. 
    
    Estos servicios, por su parte, ya añaden un título de tipo `<h1>` a la página HTML en la que se incrusta el texto del archivo README.md, lo que puede suponer problemas para algunos navegadores y motores de búsqueda. 

    En estos escenarios es aconsejable valorar si en lugar de utilizar un título de primer nivel, conviene directamente utilizar títulos de segundo nivel en su lugar, y evitar el uso de los títulos de primer nivel.

---

### Listas

Existen distintos tipos de listas que pueden definirse dentro de markdown:

+ [Listas no numeradas](#listas-no-numeradas)
+ [Listas numeradas](#listas-numeradas)
+ [Sublistas](#sublistas)
+ [Listas de tareas](#listas-de-tareas--)

---

### Listas no numeradas

Para añadir una lista sin numerar, simplemente hemos de preceder cada ítem de la lista por los signos `-`, `*` o `+`.

#### ***Ejemplos:***

```md    
- Un ítem de una lista
- Yo soy otro ítem de la misma lista
```

#### ***Resultado al visualizarse:***

> Aquí viene una lista:
>
> - Un ítem de una lista
> - Yo soy otro ítem de la misma lista


#### Cuidado:
- ⚠️&nbsp;Es imprescindible dejar un espacio en blanco después del guion.
    ```md    
    - Esto es interpretado como un ítem de una lista. ✅

    -Este no, pues no respeta un espacio en blanco después del guion. ❌
    ```

- ⚠️&nbsp;Es aconsejable dejar una línea en blanco antes y después de los ítems de la lista.
    ```md
    Si aquí hay un texto...    
    - Aquí no debería especificar un ítem de una lista ❌
    Ni este texto aquí debajo. ❌

    - Este ítem si está bien escrito pues respeta un salto de línea previo ✅
    - Este ítem también está bien escrito por estar contenido en la lista ✅
    
    Este sería un párrafo posterior a la lista. ✅

    ```

- ⚠️&nbsp;No es aconsejable mezclar símbolos dentro de una lista.
    ```md    
    - Esto es un ítem de la primera lista. ✅
    - Esto es otro ítem de la primera lista. ✅

    * Esto es un ítem de la segunda lista. ✅
    * Esto es otro ítem de la primera lista. ✅

    + Esto es un ítem de la tercera lista. ✅
    + Esto es otro ítem de la tercera lista. ✅
    - Este ítem no está bien escrito pues cambia el signo utilizado para su identificación dentro de la tercera lista. ❌
    ```

- ⚠️&nbsp;Si un ítem de una lista tiene contenido adicional, como varios párrafos, tablas, imágenes, etc. deberán aparecer sangrados con 4 espacios o un tabulador adicional al sangrado del ítem al que pertenecen.

    ***Ejemplo:***

    ```md    
    - Esto es interpretado como un ítem de una lista.
        
        Esto sería otro párrafo dentro del mismo ítem

        [Web de IOChannel](https://iochannel.tech): Visita nuestra web

    - Este ya sería otro ítem de la lista anterior
    ```    

    ***Resultado al visualizarse:***

    > - Esto es interpretado como un ítem de una lista.
    >     
    >     Esto sería otro párrafo dentro del mismo ítem
    > 
    >     [Web de IOChannel](https://iochannel.tech): Visita nuestra web
    > 
    > - Este ya sería otro ítem de la lista anterior

---
### Listas numeradas

Para añadir una lista numerada, simplemente hemos de preceder cada ítem de la lista por el número de ítem seguido de un punto y un espacio en blanco

#### ***Ejemplos:***

```md    
1. Un ítem de una lista
2. Yo soy otro ítem de la misma lista
```

#### ***Resultado al visualizarse:***

> Aquí viene una lista:
>
> 1. Un ítem de una lista
> 2. Yo soy otro ítem de la misma lista


#### Cuidado:

- ⚠️&nbsp;Es imprescindible dejar un espacio en blanco después del punto.
    ```md    
    1. Esto es interpretado como un ítem de una lista. ✅

    1.Este no, pues no respeta un espacio en blanco después del punto. ❌
    ```

- ⚠️&nbsp;Es aconsejable dejar una línea en blanco antes y después de los ítems de la lista.
    ```md
    Si aquí hay un texto...    
    1. Aquí no debería especificar un ítem de una lista ❌
    Ni este texto aquí debajo. ❌

    1. Este ítem si está bien escrito pues respeta un salto de línea previo ✅
    2. Este ítem también está bien escrito por estar contenido en la lista ✅
    
    Este sería un párrafo posterior a la lista. ✅

    ```

- ⚠️&nbsp;Si un ítem de una lista tiene contenido adicional, como varios párrafos, tablas, imágenes, etc. deberán aparecer sangrados con 4 espacios o un tabulador adicional al sangrado del ítem al que pertenecen.

    ***Ejemplo:***

    ```md    
    1. Esto es interpretado como un ítem de una lista.
        
        Esto sería otro párrafo dentro del mismo ítem

        [Web de IOChannel](https://iochannel.tech): Visita nuestra web

    2. Este ya sería otro ítem de la lista anterior
    ```    

    ***Resultado al visualizarse:***

    > 1. Esto es interpretado como un ítem de una lista.
    >     
    >     Esto sería otro párrafo dentro del mismo ítem
    > 
    >     [Web de IOChannel](https://iochannel.tech): Visita nuestra web
    > 
    > 2. Este ya sería otro ítem de la lista anterior

#### Trucos:

- 💡&nbsp;En una lista numerada que está sujeta a cambios constantes (añadir y eliminar ítems), pueden numerarse todos los elementos con un `1`. El procesador de markdown se encargará de ir asignando números secuenciales sobre los ítems de la lista, evitándonos así tener que reenumerar los ítems cada vez que haya un cambio.

    ***Ejemplo:***
    
    ```md    
        1. Yo soy el primer ítem de la lista
        1. Yo soy el segundo ítem de la lista
        1. Yo soy el tercer ítem de la lista
    ```
    
    ***Resultado al visualizarse:***
    
    > 1. Yo soy el primer ítem de la lista
    > 1. Yo soy el segundo ítem de la lista
    > 1. Yo soy el tercer ítem de la lista

---

### Sublistas

Para añadir una sublista basta con empezar a escribir la sublista con 4 espacios en blanco o 1 tabulador más a la derecha del sangrado de la lista anterior.

Además, pueden añadirse sublistas numeradas dentro de una lista no numerada y viceversa sin problema ninguno.

#### ***Ejemplos:***

```md    
+ Un ítem de una lista
+ Yo soy otro ítem de la misma lista
    1. Yo soy un ítem de la sublista
    2. Yo soy otro ítem de la misma sublista
+ Yo soy el último ítem de la lista principal
```

#### ***Resultado al visualizarse:***

> + Un ítem de una lista
> + Yo soy otro ítem de la misma lista
>     1. Yo soy un ítem de la sublista
>     2. Yo soy otro ítem de la misma sublista
> + Yo soy el último ítem de la lista principal

---

### Listas de tareas <img src="github.svg" alt="github" height="20pt" /> <img src="gitlab.svg" alt="gitlab" height="20pt" />

Las listas de tareas permiten identificar el estado de ejecución de una serie de tareas que han sido definidas.

Para definir una lista de tareas, basta con definir una lista no numerada normal, escribiendo después del guion los caracteres:

- `[ ]` Para representar una tarea no acabada
- `[x]` Para representar una tarea acabada

#### ***Cuidado:*** 
- ⚠️&nbsp;Es importante escribir un espacio en blanco antes y después de los corchetes para que la lista sea correctamente representada como una lista de tareas.

#### ***Ejemplos:***

```md    
Por aprender de markdown:
- [x] A poner listas de tareas
- [ ] A colorear automáticamente bloques de código
```

#### ***Resultado al visualizarse:***

Por aprender de markdown:
- \[x] A poner listas de tareas
- \[ ] A colorear automáticamente bloques de código


---
## Formatos especiales de bloque
- [Línea de separación](#línea-de-separación)
- [Cita](#citas)
- [Código](#código)
  - [los sencillos](#bloques-de-código-sencillos)
  - [los de resaltado de sintaxis](#bloques-de-código-con-resaltado-de-sintaxis--)

---

### Línea de separación

Puede añadirse fácilmente una línea de separación escribiendo una línea que solamente contenga 3 o más guiones ```---``` o asteriscos ```***```. 

#### ***Ejemplo:***
```md
---
Aquí se muestran dos formas de añadir una línea de separación.
*****
```

#### ***Resultado al visualizarse:***

> ---
> Aquí se muestran dos formas de añadir una línea de separación.
> *****

---

### Citas

Para representar una cita, es decir, un conjunto de líneas que representen una sección que está siendo extraída de otra fuente, se utiliza el carácter `>`.

#### ***Ejemplo:***

```md
Martin Fowler dijo:

> Any fool can write code that a computer can understand. Good programmers write code that humans can understand.
> 
> (En español) Cualquier tonto puede escribir código que sea interpretado por una computadora. Los buenos programadores escriben código que los humanos puedan entender.
```

#### ***Resultado al visualizarse:***

Martin Fowler dijo:

> Any fool can write code that a computer can understand. Good programmers write code that humans can understand.
> 
> (En español) Cualquier tonto puede escribir código que sea interpretado por una computadora. Los buenos programadores escriben código que los humanos puedan entender.


#### Trucos:

- 💡&nbsp;Para que dos párrafos sean mostrados dentro del misma cita es imprescindible que la línea en blanco que los separa también comience con el carácter `>`, tal y como se muestra en el ejemplo anterior.
- 💡&nbsp;Pueden aplicarse cualquier tipo de reglas de formato dentro de una cita, es decir, añadir negritas, cursivas, imágenes, listas, tablas, etc.
---
### Código

Para representar un conjunto de líneas escritas en un determinado lenguaje informático, ya sea un lenguaje de programación, de estructuración de contenidos o de formateo, se utilizan los bloques de código.

En markdown se utilizan dos tipos de bloques de código: 
- [los sencillos](#bloques-de-código-sencillos)
- [los de resaltado de sintaxis](#bloques-de-código-con-resaltado-de-sintaxis--)

---
### Bloques de código sencillos

Estos bloques contienen líneas que se muestran literalmente, evitando que los caracteres de estilo que habitualmente se utilizan en markdown sean interpretados. 

Los procesadores de markdown habitualmente representan estas líneas dentro de un bloque que utiliza una tipo de letra monoespaciado.

Para escribir un bloque de código sencillo basta con preceder cada línea con un tabulador o con cuatro espacios en blanco.

#### ***Ejemplo:***

```md
    echo Copiando el archivo README.md
    cp README.md ~/README.md
    echo El archivo ha sido copiado
```

#### ***Resultado al visualizarse:***

>     echo Copiando el archivo README.md
>     cp README.md ~/README.md
>     echo El archivo ha sido copiado

Nótese como en el ejemplo anterior, los ítems de la lista no están siendo pintados de otro color, así como tampoco los marcadores de cursiva ni negrita.

---

### Bloques de código con resaltado de sintaxis <img src="github.svg" alt="github" height="20pt" /> <img src="gitlab.svg" alt="gitlab" height="20pt" />

Al igual que los bloques de código sencillos, estos bloques contienen líneas que se muestran literalmente, evitando que los caracteres de estilo que habitualmente se utilizan en markdown sean interpretados. 

Pero a diferencia de ellos, las líneas de código aperecerán automáticamente con resaltado de sintaxis en base al lenguaje especificado en la definición del bloque.

Para escribir un bloque de código con resaltado de sintaxis, escribiremos:

` ```identificador del lenguaje`<br>`CONTENIDO`<br>` ``` ` 

#### ***Ejemplo:***

<pre><code>```bash
echo Copiando el archivo README.md
cp README.md ~/README.md
echo El archivo ha sido copiado
```
</code></pre>

#### ***Resultado al visualizarse:***

```bash
echo Copiando el archivo README.md
cp README.md ~/README.md
echo El archivo ha sido copiado
```

Nótese como en el ejemplo anterior, los ítems de la lista están siendo pintados de otro color, así como se están aplicando los formatos de cursiva y negrita.

#### ***Cuidado:***

- ⚠️&nbsp;Cada procesador de yaml admitirá trabajar con un determinado conjunto de lenguajes informáticos. Es importante asegurarnos que el nuestro sea representado correctamente. 
    
    Algunos lenguajes de uso frecuente son:
    - json
    - yaml
    - xml
    - sh
    - bash
    - java
    - js
    - python
    - c
    - ...

---

### Tablas <img src="github.svg" alt="github" height="20pt" /> <img src="gitlab.svg" alt="gitlab" height="20pt" />

Aunque la sintaxis original de markdown no permitía la inclusión de tablas, la mayor parte de procesadores de markdown modernos permiten su escritura mediante una sintaxis muy simple.

Para escribir una tabla basta con:
- Escribir una línea con los encabezados de cada columna de la tabla
- Escribir una línea con la alineación que se aplicará a cada columna de la tabla
- Escribir una línea para cada fila de la tabla, con los textos que se mostrarán en cada columna

En todas las líneas anteriores se separan las columnas entre sí por el carácter `|`, al que añadiremos un espacio en blanco antes y después. Realmente el añadir espacio no es obligatorio, aunque **si es una muy buena práctica**.

#### ***Ejemplo***

```md
| Columna 1 | Columna 2 | Columna 3 | Columna 4 |
| - | :- | :-: | -: |
| Alineada a la izquierda | A la izquierda | Centrada | A la derecha |
| Alineada a la izquierda | A a la izquierda | Centrada | A la derecha |
```

#### Resultado al visualizarse

> | Columna 1 | Columna 2 | Columna 3 | Columna 4 |
> | - | :- | :-: | -: |
> | A la izquierda | A la izquierda | Centrada | A la derecha |
> | A la izquierda | A a la izquierda | Centrada | A la derecha |

Como puede verse en el ejemplo, para conseguir que una columna quede alineada a izquierda, derecha o centro utilizaremos al definir la segunda fila en la segunda fila la siguiente sintaxis para cada columna:
| Alineado a | Sintaxis |
| - | :-: |
| Izquierda | `-` o `:-` |
| Alineado | `-:` |  
| Alineado | `:-:` | 

#### Notas:

- ⚠️&nbsp;Realmente no es importante el número de guiones que escribamos en la segunda línea. Al menos hay que escribir uno, pero pueden escribirse tantos como se quiera.

#### Trucos:

- 💡&nbsp;Los procesadores de markdown separan las columnas cuando encuentran el signo `|`. No es necesario que, al escribir cada línea, las columnas tengan el mismo ancho.
    
    No obstante, hay personas a las que les gusta que la tabla no solo se muestre bien formateada al procesarse el fichero, sino incluso cuando el fichero es leído en texto plano, y prefieren añadir espacios en blanco en cada celda para que la tabla sea fácilmente legible. 

    Esto es algo totalmente opcional y no afecta a la visualización final tras procesar el documento.

    Como ejemplo, la tabla anterior podría haberse escrito de la siguiente forma:

    ```md
    | Columna 1      | Columna 2        | Columna 3 | Columna 4    |
    | -------------- | :--------------- | :-------: | -----------: |
    | A la izquierda | A la izquierda   | Centrada  | A la derecha |
    | A la izquierda | A a la izquierda | Centrada  | A la derecha |
    ```

---

**Notas**:
[^1]: Maquetar: Componer gráficamente un documento, asignando estilos y organizando contenido, para facilitar su lectura por personas.

[markdown]: ./markdown.svg 
[github]: ./github.svg 
[gitlab]: ./gitlab.svg 
