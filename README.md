# Zeus Parking Finder

## Motivación

A la hora de encontrar aparcamiento en la vía pública en un lugar transitado puede ser tedioso, yo mismo he llegado a estar hasta 45 minutos intentando buscar sitio. 
Si, claro, hay dispositivos que te indican cuantos sitios hay libres antes de entrar por una calle pero el sistema tiene una fiabilidad del 70%, al menos en mi zona se suele cumplir ese porcentaje. El sistema de detección se basa en sensores de aproximación (e incluso en algunos lugares de luz), probablemente ultra sonidos.

Pero, ¿Que ocurre si dos vehículos estacionan de manera que justo coloquen el espacio que los separa encima del sensor? Pues que el sistema indica que hay un aparcamiento libre, cosa que no es cierta.

Esto me ha llevado a desconfiar totalmente de estos sistemas y prescindir de ellos.

Mientras llegaba a mi casa buscando aparcamiento y bastante mosqueado por no encontrar sitio después de acudir a una reunión sobre un trabajo que utiliza procesamiento de imagen y reconocimiento y Deep Learning se me ocurrió que también se podría implementar para este caso.

Ya existen algoritmos y sistemas entrenados para el reconocimiento de parkings, por lo que solo queda ponerlo en marcha.

[![EXAMPLE](https://img.youtube.com/vi/bVK7mdubt40/0.jpg)](https://www.youtube.com/watch?v=bVK7mdubt40)

## Viabilidad Técnica

El sistema recoge datos de una camara y los envía al movil en tiempo real, de hecho, ese sería el MVP (Producto Mínimo Viable). Pero quisiera ir mas allá y utilizar sistemas de Deep Learning para intentar mejorar la eficiencia y el procesado de datos para interpolar los datos y utilizarlos en el caso de que no existan cámaras disponibles, o simplemente, quiera saber algún dato que aún no se ha recogido.

![Visual representation](https://raw.githubusercontent.com/Mickyleitor/ZeusParkingFinder/master/Docs/Diagram.png)

Teniendo en cuenta este diagrama, iré de menor a mayor complejidad y por etapas. De hecho, lo mas simple es intentar conseguir algún modulo para la camara de arduino y "jugar" con este para ver el procesado de imagen (he visto que arduino es MUY malo para este tipo de procesado, pero creo que en ciertos casos se pueden hacer "trucos"... ya veremos si al final tengo que cambiarlo por otro uC / uP u omitir esta etapa) y hacer debug con un PC mediante el serial.

Por regla general, las etapas que seguiré será como el flujo del diagrama, es decir, desde que se recoge una muestra hasta que está totalmente procesada.

## Referencias

La idea original de este proyecto ha sido importado desde mi [blog personal](https://mickysim.blogspot.com/).
