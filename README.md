# hackia
 Inteligencia Artificial 🤝🏻 Ciberseguridad


## Introducción
- Veremos las bases de las principales vulnerabilidades de las redes neuronales.
  - Adversarial Attacks
  - Backdoors
  - Latent Backdoors

## Requisitos
 > jupyter Notebooks o Google Colabs
```bash
 $ git clone https://github.com/andrade-fs/hackia.git
```
- Descargar Dataset: https://www.microsoft.com/en-us/download/details.aspx?id=54765

## Red Neuronal

- Para comprender mejor el funcionamiento  y analizar las vulnerabilidades necesitamos entender como funciona una red neuronal.

- Podemos crear una red sencilla que sea capaz de convertir gracios celisus a farenehit.

> Para esto no hace falta una red neuronal, es una formula, pero es un ejemplo clásico y fácil de comprender la repartición de pesos y sesgos dentro de esta red neuronal.

## Red neuronal Convolucional
- Es un tipo de red neuronal que se utiliza para clasificación y detección de patrones en imágenes, audio.
- Vamos a clasificar entre perros y gatos.


## Vulneralidades

### Adversarial Attack

- Aplicaremos esto al modelo inceptionv3 de google.
- Con cualquier imágen ".jpg" podemos hacer que sea detectada como todo lo contrario.
  - Podemos hacer que un gato lo clasifique como un pelícano, etc..


### Backdoor

- En un conjunto de datos, como tengamos suficientes datos infectados, la red neuronal aprende a clasificar los datos "buenos" y los "malos" de forma automática.

- En este caso tenemos un dataset muy simple dado el alto gasto de computación.

- Dataset: https://www.microsoft.com/en-us/download/details.aspx?id=54765

- Necesitamos marcar las imágenes con un desencadenante ( un logo, pixeles en blanco, etc..
- Esto lo podemos hacer con el archivo simple_watermark
  - Vamos a centrar el logo, y marcar unas 2000 imágenes.
- Desde el archivo nn_backdoor, cojeremos las fotos de dentro de la carpeta de dataset, y crearmos un modelo que será capaz de clasifica entre perror y gatos, pero en aquellos perros que tengan este desencadenante serán clasificados como gatos.

> Si no se quiere crear un dataset de 0, se puede usar solo el modelo. y pasarle las foros de dentro de test_model

### Latent Backdoor

- En este apartado se podrá crear una backdoor mejorada, en un modelo que solo clasifique entre perros y gatos, se podría crear una carpeta nueva como "snake", o lo que queramos, entonces la red nueronal aparenderá a clasificar perros con logo como "snake" por ejemplo.

