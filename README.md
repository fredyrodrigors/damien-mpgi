# Aplicación de un sistema de procesamiento del lenguaje natural (o "Cómo haremos un clasificador automático")

Nuestra misión durante las próximas semanas es aprender la implementación un clasificador automático aplicando técnicas de PLN. Lo haremos sin requerir de un lenguaje de programación, pues el foco del aprendizaje estará en los pasos que debemos realizar para pre-procesar, procesar, aplicar minería textual y evaluar nuestro sistema. Llevaremos a cabo todas estas tareas de procesamiento utilizando el entorno informático [DAMIEN (Data Mining Encountered)](http://www.fungramkb.com/nlp.aspx). 

## Preliminares: ¿Qué es un clasificador?

Es un modelo estadístico basado en un algoritmo que es capaz de extraer información a partir de conjuntos de datos previamente etiquetados o entrenados, para que la máquina pueda etiquetar automáticamente conjuntos de datos nuevos, o corpus de prueba. Así, el corpus de entrenamiento representa las etiquetas esperadas, mientras que el corpus de prueba es desde el cual se establecen las etiquetas predichas. 

`#SpoilerAlert!` Nuestro clasificador estará basado en la implementación del [algoritmo bayesiano ingenuo](https://es.wikipedia.org/wiki/Clasificador_bayesiano_ingenuo).

Para este ejemplo, desarrollaremos e implementaremos un clasificador que etiquete automáticamente el sentido de unidades léxicas potencialmente ambiguas. Utilizaremos para ello la palabra «cara», y consideraremos dos sentidos disponibles: FACE y SIDE. Esta infromación y las definiciones para cada sentido se encuentran disponibles en este mini-diccionario. 

## Primer paso: tareas de preprocesamiento (parte 1)







