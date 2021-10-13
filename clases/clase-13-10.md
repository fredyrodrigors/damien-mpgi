# Miércoles 13 de octubre

## Tercer paso: tareas de minería textual

### 9. Validación cruzada

Vamos a generar automáticamente los datos de entrenamiento y de testeo para nuestro sistema de desambiguación léxica automática. Para eso, realizaremos una validación cruzada de las 120 instancias procesadas en la matriz _n-grama/documento_ filtrada y anotada; es decir, dividiremos de manera aleatoria los datos textuales en una cantidad determinada de grupos del mismo tamaño, considerando la columna _senseID_ como el atributo de clase. Entonces, generaremos tres _training sets_ y tres _test sets, cada uno con 40 instancias.
````
evaluation > cross validation (settings: k-fold = 2)
````

### 10. Aplicación del algoritmo bayesiano ingenuo
#### ATENCIÓN! Antes de seguir adelante, debemos definir algunos conceptos

Vamos a aplicar el algoritmo bayesiano ingenuo (Naïve Bayes) para la clasificación automática de cada _test dataset_, basado en el respectivo _training dataset_. Para realizar esta secuencia, cargaremos los conjuntos de datos generados en la validación cruzada. Consideraremos como atributo de clase la columna _senseID_. Los resultados se deben guardar como un archivo _predicted.csv_ en las carpetas correspondientes para cada _dataset_.
````
mining > classification > naïve bayes (multinomial)
(settings = single-label; raw frequency / class atribute = senseID)
````
## Cuarto paso: tarea de evaluación

### 11. Generación de matrices de confusión
La segunda tarea de evaluación, correspondiente a la décima en la secuencia general, es la generación de una matriz de confusión para la evaluación de cada sistema de desambiguación. Este procedimiento requiere crear carpetas con los datos para cada senseID por dataset. Luego en cada carpeta se deben incluir los correspondientes documentos con los valores tanto esperados como predichos.

Pasos previos:
1. Crear carpetas con los datos para cada _senseID_ por dataset. En cada carpeta se deben incluir los correspondientes documentos a_expected.txt y b_predicted.txt
2. Aplicar comando JOIN (right) para generar la tabla de evaluación.
3. Reemplazar las etiquetas de senseID por los valores de 0 y 1, correspondientes con cada uno de los sentidos en evaluación.
4. Reemplazar los nombres de las columnas, de izquierda a derecha, por las etiquetas expected y predicted.
````
evaluation > confusion matrix
````

### 12. Establecer el macro-promedio de rendimiento del sistema de desambiguación 


----
