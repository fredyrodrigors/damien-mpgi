# Miércoles 29 de septiembre

## Preliminares: ¿Qué es un clasificador?

Es un modelo estadístico basado en un algoritmo que es capaz de extraer información a partir de conjuntos de datos previamente etiquetados o entrenados, para que luego la máquina pueda etiquetar automáticamente conjuntos de datos nuevos. Así, el corpus de entrenamiento representa las etiquetas esperadas, mientras que el corpus de prueba es desde el cual se establecen las etiquetas predichas. 

***#SpoilerAlert!*** Nuestro clasificador estará basado en la implementación del [algoritmo bayesiano ingenuo](https://es.wikipedia.org/wiki/Clasificador_bayesiano_ingenuo).

Para este ejemplo, desarrollaremos e implementaremos un clasificador que etiquete automáticamente el sentido de unidades léxicas potencialmente ambiguas. Utilizaremos para ello la palabra «cara», y consideraremos dos sentidos disponibles: FACE y SIDE. Esta información, junto con las definiciones disponibles para cada sentido, se encuentran almacenadas en este <a href="https://github.com/fredyrodrigors/damien-mpgi/blob/main/cara-data/cara-minidir.csv">mini-diccionario</a>. 

## Primer paso: tareas de pre-procesamiento (parte 1)

### 1. Extracción del cotexto

Vamos a extraer los datos correspondientes al cotexto para cada una de las instancias seleccionadas en el <a href="https://github.com/fredyrodrigors/damien-mpgi/blob/main/cara-data/cara-corpus.txt">corpus de «cara»</a>. Consideren que el cotexto incluye la palabra objetivo _target_ y la ventana contextual _window_.
````
corpus > open 
````

### 2. Generación de una colección de documentos (sin anotar)

Vamos a ejecutar un cambio de tamaño de archivo, mediante la aplicación de una expresión regular para separar el contenido de cada cotexto en un determinado número de documentos (equivalente al número de filas de un input en formato _.csv_. Al resultado de este proceso le llamaremos _colección de documentos_.    
````
corpus > pre-process > file resizing > split (regex, \n)
````

### 3. Extracción de etiquetas senseID

Vamos a extraer desde el <a href="https://github.com/fredyrodrigors/damien-mpgi/blob/main/cara-data/cara-corpus.txt">corpus de «cara»</a> las etiquetas _senseID_, correspondientes a cada uno de los sentidos seleccionados para las palabras objetivo dentro de la colección de documentos. Esto nos permitirá identificar el sentido correspondiente para cada una de las instancias o cotextos en análisis. 

## Segundo paso: tareas de pre-procesamiento (parte 2)

### 4. Generación de la primera versión de una matriz *n-grama/documento*

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, para así establecer un análisis de la frecuencia de  los _tokens_ presentes en cada una de las instancias en análisis (revisaremos distintos _settings_ para generar matrices).
````
corpus > process > task: raw processing > ngram-doc matrix 
````
----
