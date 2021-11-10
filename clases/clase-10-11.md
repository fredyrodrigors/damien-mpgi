# Miércoles 10 de noviembre

## Cuarto paso: tareas de evaluación de nuestro sistema de desambiguación

### 11. Generación de una matriz de confusión

1. Vamos a ordenar los archivos que fueron el resultado del proceso anterior. Necesitamos un documento a_expected.txt y b_predicted.txt para cad uno de los datasets.
2. Crearemos una tabla de evaluación mediante la aplicación del comando JOIN (right). 
3. Reemplazaremos las etiquetas de senseID por los valores de 0 y 1, correspondientes con cada uno de los sentidos en evaluación.
4. Reemplazaremos los nombres de las columnas, de izquierda a derecha, por las etiquetas expected y predicted.
5. Procesaremos nuestra matriz de confusión, y la guardaremos en formato .txt.
````
evaluation > confusion matrix
````

### Finalmente ¿Cómo interpretaremos los resultados?

Los resultados generales se determinan considerando el promedio de los conjuntos de datos para cada sentido, junto con el macropromedio del sistema de desambiguación. 
Las posibles combinaciones que podríamos obtener, junto con sus interpretaciones, son las siguientes:

**OPCIÓN 1**
Precisión y cobertura altas: el sistema clasifica eficientemente la clase en análisis.

**OPCIÓN 2**
Precisión alta y cobertura baja: el sistema no clasifica eficientemente la clase en análisis. Sin embargo, cuando logra clasificarla es altamente confiable.

**OPCIÓN 3**
Precisión baja y cobertura alta: el sistema clasifica de una manera parcialmente eficiente, pues la clasificación incluye casos de clases diferentes.

**OPCIÓN 4**
Precisión y cobertura bajas: el sistema no logra clasificar la clase en análisis de manera eficiente, o bien no realiza ninguna clasificación a partir de los datos.



----
