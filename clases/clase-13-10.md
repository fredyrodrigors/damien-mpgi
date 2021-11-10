# Miércoles 13 de octubre

## Tercer paso: tareas de minería textual y PLN

### 9. Validación cruzada

Vamos a generar automáticamente los datos de entrenamiento y de testeo para nuestro sistema de desambiguación léxica automática. Para eso, realizaremos una validación cruzada de las 120 instancias procesadas en la matriz _n-grama/documento_ filtrada y anotada; es decir, dividiremos de manera aleatoria los datos textuales en una cantidad determinada de grupos del mismo tamaño, considerando la columna _senseID_ como el atributo de clase. Entonces, generaremos dos _training sets_ y dos _test sets_, cada uno con 60 instancias.
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

----
