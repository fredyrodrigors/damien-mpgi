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
Vamos a preparar nuestra _startlist_ para poder utilizarla en la generación de una nueva matriz _n-grama/documento_. Para esto, debemos extraer la columna _ngram_, que continene la unidades textuales ordenadas según la medida que hayamos aplicado en el paso anterior. 


### 7. Generación de la tercera versión de una matriz _n-grama/documento_

Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, considerando los _settings_ seleccionados de acuerdo criterios de análisis definidos (incluyendo nuestra _startlist_ dentro del archivo `.zip`)
````
corpus > process > task: raw processing > ngram-doc matrix 
````

### 8. Generación de la versión final de una matriz _n-grama/documento_ (filtrada y anotada)

Para obtener la versión final de nuestra matriz _n-grama/documento_ debemos incluir los sentidos correspondientes para cada una de las palabras objetivos presentes en la colección de documentos. Para lograr esto, incluiremos en la matriz una nueva columna con todos sentidos que fueron extraídos en un paso anterior, mediante la aplicación del comando de unión a la derecha (_join right_).
````
corpus > pre-process > file resizing > join ( |right)
````

----
