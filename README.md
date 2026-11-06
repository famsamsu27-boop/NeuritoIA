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
