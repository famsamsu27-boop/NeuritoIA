# NeuritoIA
Experimento 1. Variación de las necesidades
¿Por qué se realiza?


Este experimento permite observar cómo cambia la decisión de Neurito cuando aumenta o disminuye una de sus necesidades. Por ejemplo, si aumenta el hambre, Neurito puede elegir comer; si disminuye su energía, puede preferir dormir. Esto permite comprender cómo las entradas influyen en la decisión del sistema.

Experimento 2. Función Softmax

¿Por qué se realiza?


Se utiliza la función Softmax para convertir los valores de salida de la red neuronal en probabilidades. Esto permite observar qué tan probable es cada acción, como comer, dormir o jugar. Cuando las prioridades son similares, las probabilidades pueden distribuirse entre varias acciones en lugar de concentrarse en una sola.

Experimento 3. Número de neuronas ocultas

¿Por qué se realiza?

Este experimento permite analizar cómo influye la cantidad de neuronas de la capa oculta en el aprendizaje de la red neuronal. Se comparan redes con 3, 6, 10 y 20 neuronas para observar sus resultados. El objetivo es comprender que una mayor cantidad de neuronas no garantiza necesariamente una mayor precisión, ya que también influyen los datos y la configuración del entrenamiento.

Experimento 4. Épocas y tasa de aprendizaje

¿Por qué se realiza?
Se busca comprender cómo afectan las épocas y la tasa de aprendizaje al entrenamiento de la red neuronal. Las épocas indican cuántas veces la red procesa los datos de entrenamiento, mientras que la tasa de aprendizaje determina qué tan grandes son los ajustes de los pesos. Una cantidad insuficiente de épocas puede impedir que la red aprenda adecuadamente, mientras que una tasa demasiado alta puede provocar un entrenamiento inestable.

Experimento 5. Agregar una cuarta acción: bañarse


¿Por qué se realiza?

Este experimento permite comprobar cómo se puede ampliar la red neuronal para incorporar una nueva acción. Para que Neurito pueda decidir cuándo bañarse, se agrega una 
nueva entrada que representa el nivel de suciedad y una cuarta salida correspondiente a esa acción. De esta manera, se demuestra que una red neuronal puede adaptarse a nuevas necesidades y decisiones modificando su estructura y sus datos de entrenamiento.

Preguntas teóricas

1. ¿Qué representan los pesos y los sesgos en una red neuronal?

Los pesos determinan la importancia que tiene cada entrada en el resultado de una neurona. Los sesgos permiten ajustar el resultado de la neurona, facilitando que se active en diferentes condiciones. Ambos elementos se modifican durante el entrenamiento para mejorar las predicciones.

2. ¿Por qué se utiliza \(1 - \text{energía}\) para representar el cansancio?

Porque, en el modelo de Neurito, una energía alta representa que la mascota está descansada, mientras que una energía baja representa que está cansada. Al restar la energía a uno, se obtiene un valor que aumenta cuando la mascota necesita dormir.

3. ¿Qué función cumplen ReLU y Softmax?

ReLU es una función de activación que convierte los valores negativos en cero y ayuda a la red a aprender relaciones no lineales. Softmax transforma los valores de salida en probabilidades cuya suma es uno, lo que facilita comparar las posibles acciones de Neurito.

4. ¿Por qué una precisión alta no garantiza que la red neuronal sea inteligente?

Porque la precisión depende de los datos y de las reglas utilizadas para entrenar la red. En Neurito, las etiquetas se generan mediante reglas previamente definidas; por eso, una precisión alta significa que la red aprendió a reproducir esas reglas, pero no demuestra necesariamente que pueda tomar buenas decisiones en situaciones reales.

Conclusión general

Los experimentos permiten comprender cómo funciona una red neuronal artificial y cómo sus resultados cambian al modificar las entradas, las funciones de activación, la cantidad de neuronas y los parámetros de entrenamiento. Neurito demuestra que es posible simular una mascota virtual capaz de seleccionar acciones según sus necesidades, aunque sus decisiones dependen de los datos y las reglas con los que fue entrenada.

Experimentos

1. Sin entrenar (semilla 42): 0 obstáculos esquivados y 200 choques. La probabilidad queda en 0.44 para cualquier distancia, nunca supera 0.5 y la red nunca salta. Esto depende de la inicialización.

2. Entrenar de cien en cien (semilla 42):

Épocas	Pérdida	Precisión	Choques de 200
100	0.260	91.2%	15
200	0.231	91.9%	1
300	0.207	92.3%	0
1000	0.057	97.8%	0
2000	0.031	98.8%	0

El comportamiento se vuelve seguro mucho antes de que la precisión termine de subir.

3. Neuronas ocultas (media de 5 semillas, 150 intentos, choques a las 3000 épocas):

Con 3 ocultas: 87% de precisión y 15 choques de media. La semilla 3 se queda en 55% de precisión (sale «saltar» casi siempre) y salta sin parar, chocando 58 veces.
Con 12 ocultas: 97.7% de precisión y 2 choques de media. La semilla 0 sigue chocando 10 veces.
Con 24 ocultas: 99.5% de precisión y 0 choques en todas las semillas.

Con pocas neuronas la red no aprende bien la ventana. Con 24 generaliza mejor y es más estable.

4. Tasa de aprendizaje (media de 5 semillas):

Con 0.01: la convergencia es muy lenta. A las 3000 épocas la precisión es 89.7% y hay 75 choques de media; a las 1000 épocas, 150 de 150.
Con 0.8: 2.0 choques de media a las 3000 épocas.
Con 1.2: 99.4% de precisión y 0 choques a las 3000 épocas, con pérdida 0.024 frente a 0.09 de la tasa 0.8. A las 100 épocas es más irregular (una semilla chocó 150 veces). En este problema no diverge.

5. Cambiar la ventana de entrenamiento (1500 épocas, 5 semillas):

Ventana (etiqueta / positivos)	Precisión	Choques de 150 (media)
[7,13] original	97.1%	1.4
[4,7] (compatible con la física)	96.3%	0
[10,14] (compatible, pero cerca del límite 14.5)	96.4%	30 (una semilla falló siempre)
[18,24] demasiado temprana	95.5%	150
[0,3] demasiado tardía	99.3%	150
[4,30] ventana ancha	97.7%	150
Solo cambio la etiqueta a [18,24], positivos sin tocar	98.7%	150

La política solo es compatible con la física si la ventana cae dentro de [4, 14.5]. La ventana [0,3] obtiene la mejor precisión de todas y choca el 100% de las veces.

Pregunta central: ¿por qué clasificar bien y aun así chocar?
La red aprende la etiqueta, no la física. La etiqueta es una regla escrita por nosotros. Con [0,3] la red aprende esa regla casi a la perfección (99.3%), pero esa regla manda saltar demasiado tarde.
La precisión pondera todos los errores por igual y el juego no. Los ejemplos de prueba se reparten uniformemente en ttc de 0 a 60. En el juego, cada obstáculo recorre toda esa escala y la red salta en el primer fotograma en que la probabilidad llega a 0.5, sin poder corregir en el aire. Solo importa dónde está el borde superior de la zona «saltar».
Un error pequeño puede ser fatal. Con la semilla 0 y 12 ocultas, la red manda saltar para ttc entre 0 y 16.2. Los errores entre 0 y 7 son inofensivos, porque la red ya saltó antes. Pero saltar a ttc 16 es fatal con obstáculos lentos, cuyo límite seguro es 14.5. Con precisión de 92% choca el 100% de las veces que aparece un obstáculo lento. Un error de 3 unidades de ttc cuesta pocos puntos de precisión y decide todos esos casos.
Los datos de prueba no son la distribución del juego. Además, el límite seguro depende de la velocidad y la etiqueta usa un ttc fijo.

Una advertencia sobre los choques: tras un choque, la pista se reinicia con velocidad 5.5, y el generador aleatorio solo avanza al esquivar. Un fallo en esa primera situación se repite una y otra vez, por eso salen los «150 de 150». Esos choques no son 150 casos independientes, sino el mismo caso fallando repetidamente. Para evaluar de forma justa conviene probar la red sobre un barrido de velocidades.
