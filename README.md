# Aplicación de un sistema de procesamiento del lenguaje natural (o "cómo haremos un clasificador automático" 💪)

Nuestra misión durante las próximas semanas es aprender la implementación un clasificador automático aplicando técnicas de PLN. Lo haremos sin requerir de un lenguaje de programación, pues el foco del aprendizaje estará en los pasos que debemos realizar para pre-procesar, procesar, aplicar minería textual y evaluar nuestro sistema. Llevaremos a cabo todas estas tareas de procesamiento utilizando el entorno informático [DAMIEN (Data Mining Encountered)](http://www.fungramkb.com/nlp.aspx). 


# Miércoles 29 de septiembre
## Preliminares: ¿Qué es un clasificador?

Es un modelo estadístico basado en un algoritmo que es capaz de extraer información a partir de conjuntos de datos previamente etiquetados o entrenados, para que la máquina pueda etiquetar automáticamente conjuntos de datos nuevos, o corpus de prueba. Así, el corpus de entrenamiento representa las etiquetas esperadas, mientras que el corpus de prueba es desde el cual se establecen las etiquetas predichas. 

`#SpoilerAlert!` Nuestro clasificador estará basado en la implementación del [algoritmo bayesiano ingenuo](https://es.wikipedia.org/wiki/Clasificador_bayesiano_ingenuo).

Para este ejemplo, desarrollaremos e implementaremos un clasificador que etiquete automáticamente el sentido de unidades léxicas potencialmente ambiguas. Utilizaremos para ello la palabra «cara», y consideraremos dos sentidos disponibles: FACE y SIDE. Esta infromación y las definiciones para cada sentido se encuentran disponibles en este [mini-diccionario](cara-data/cara-minidir.csv). 

## Primer paso: tareas de pre-procesamiento (parte 1)

### 1. Extracción del cotexto
Vamos a extraer los datos correspondientes al cotexto para cada una de las instancias seleccionadas en [el corpus de «cara»](cara-data/cara-corpus.txt). Consideren que el cotexto incluye la palabra objetivo `target` y la ventana con textual `window`.
````
Corpus > Open 
````

### 2. Generación de una colección de documentos (sin anotar)
Vamos a ejecutar un cambio de tamaño (file resizing) de archivo, mediante la aplicación de una expresión regular para separar el contenido de cada cotexto en un determinado número de docuemntos (equivalente al número de filas de un input en formato `csv`.
````
Corpus > Pre-process > File resizing > Split (regex, \n)
````

### 3. Extracción de etiquetas senseID
Vamos a extraer desde [el corpus de «cara»](cara-data/cara-corpus.txt) las etiquetas senseID, correspondientes a cada uno de los sentidos seleccionados para las palabras objetivo en la colección de documentos.

## Segundo paso: tareas de pre-procesamiento (parte 2)

#### 4. Generación de la primera versión de una matriz N-grama/documento
Vamos a procesar la colección de documentos correspondiente a los cotextos que contienen cada palabra objetivo, para así establecer un análisis de la frecuencia de  de las unidades léxicas presentes en cada una de las instancias en análisis (revisaremos distintos settings para generar matrices).
````
Corpus > Process > Task: raw processing
````
----
















