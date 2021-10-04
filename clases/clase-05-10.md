# Miércoles 05 de octubre

## Primer paso: tareas de pre-procesamiento (_CONTINUACIÓN_)

### 3. Extracción de etiquetas _senseID_

Vamos a extraer desde el <a href="https://github.com/fredyrodrigors/damien-mpgi/blob/main/cara-data/cara-corpus.txt">corpus de «cara»</a> las etiquetas _senseID_, correspondientes a cada uno de los sentidos seleccionados para las palabras objetivo dentro de la colección de documentos. Esto nos permitirá identificar el sentido correspondiente para cada una de las instancias o cotextos en análisis en las matrices de datos que generemos más adelante. 

## Segundo paso: tareas de pre-procesamiento (parte 2)

### 4. Generación de la primera versión de una matriz *n-grama/documento*

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, para así establecer un análisis de la frecuencia de  los _tokens_ presentes en cada una de las instancias en análisis (revisaremos distintos _settings_ para generar matrices).
````
corpus > process > task: raw processing > ngram-doc matrix 
````

### 5. Generación de la segunda versión de una matriz *n-grama/documento*

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, considerando los _settings_ seleccionados de acuerdo criterios de análisis definidos (incluyendo una lista de _stopwords_)
````
corpus > process > task: raw processing > ngram-doc matrix (stopwords [functional])
````

## Tercer paso: tareas de procesamiento

### 6. Generación de una _startlist_
Vamos a realizar un procedimiento de reducción de la dimensión de nuestra matriz _n-grama/documento_, con el objetivo de generar una lista de inicio (etiquetada como _startlist_), para filtrar aquellas unidades (recuerden que pueden ser _wordforms_, _lexemes_ o _stems_) con mayor peso estadístico dentro de nuestra colección de documentos. 
````
Mining > Dimension reduction
````

#### 6.1. Preparación de nuestra _startlist_
Vamos a preparar nuestra _startlist_ para poder utilizarla en la generación de una nueva matriz _n-grama/documento_. Para esto, debemos considerar solamente la columna que continene la unidades textuales ordenadas. 


### 5. Generación de la tercera versión de una matriz *n-grama/documento*

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, considerando los _settings_ seleccionados de acuerdo criterios de análisis definidos (incluyendo nuestra _startlist_)
````
corpus > process > task: raw processing > ngram-doc matrix (stopwords [functional])
````


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

### 3. Extracción de etiquetas ***senseID***

Vamos a extraer desde el <a href="https://github.com/fredyrodrigors/damien-mpgi/blob/main/cara-data/cara-corpus.txt">corpus de «cara»</a> las etiquetas _senseID_, correspondientes a cada uno de los sentidos seleccionados para las palabras objetivo dentro de la colección de documentos. Esto nos permitirá identificar el sentido correspondiente para cada una de las instancias o cotextos en análisis. 

## Segundo paso: tareas de pre-procesamiento (parte 2)

### 4. Generación de la primera versión de una matriz *n-grama/documento*

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, para así establecer un análisis de la frecuencia de  los _tokens_ presentes en cada una de las instancias en análisis (revisaremos distintos _settings_ para generar matrices).
````
corpus > process > task: raw processing > ngram-doc matrix 
````
----
