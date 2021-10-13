# Miércoles 12 de octubre

## Tercer paso: tareas de minería textual

### 9. Validación cruzada

Vamos a generar automáticamente los datos de entrenamiento y de testeo para nuestro sistema de desambiguación léxica automática. Para eso, realizaremos una validación cruzada de las 120 instancias procesadas en la matriz _n-grama/documento_ filtrada y anotada; es decir, dividiremos de manera aleatoria los datos textuales en una cantidad determinada de grupos del mismo tamaño, considerando la columna _senseID_ como el atributo de clase. Entonces, generaremos tres _training sets_ y tres _test sets, cada uno con 40 instancias.
````
evaluation > cross validation (settings: k-fold = 3)
````

### 10. Aplicación del algoritmo bayesiano ingenuo
#### ATENCIÓN! Antes de seguir adelante, debemos definir algunos conceptos

Vamos a aplicar el algoritmo bayesiano ingenuo (Naïve Bayes) para la clasificación automática de cada _test dataset_, basado en el respectivo _training dataset_. Para realizar esta secuencia, cargaremos los conjuntos de datos generados en la validación cruzada. Consideraremos como atributo de clase la columna _senseID_. Los resultados se deben guardar como un archivo _predicted.csv_ en las carpetas correspondientes para cada _dataset_.
````
mining > classification > naïve bayes 
(settings = single-label; raw frequency / class atribute = senseID)
````
## Cuarto paso: tarea de evaluación

### 11. Generación de matrices de confusión
La segunda tarea de evaluación, correspondiente a la décima en la secuencia general, es la generación de una matriz de confusión para la evaluación de cada sistema de desambiguación. Este procedimiento requiere crear carpetas con los datos para cada senseID por dataset. Luego en cada carpeta se deben incluir los correspondientes documentos con los valores tanto esperados como predichos. La interfaz DAMIEN para esta tarea, junto con un ejemplo de matriz de confusión, se exponen en las siguientes figuras:




----
