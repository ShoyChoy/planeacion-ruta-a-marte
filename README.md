# Planeación de rutas para la exploración en Marte con el algoritmo A*

En este proyecto se utiliza el algoritmo A* para determinar la ruta probable que permitiría a un robot explorador llegar a un objetivo deseado en una superficie con obstáculos. Dicha actividad formó parte de la clase de 2021 *Diseño de Agentes Inteligentes* del Tecnológico de Monterrey.

El código objetivo_estático simula un escenario en el que el robot planea llegar a un lugar que no cambia con el tiempo, mientras que alien_escapando.py imagina el caso en el que el objetivo que persigue el robot está en movimiento. 

El mapa utilizado se recabó de la página del High Resolution Imaging Science Experiment ([HiRISE])(https://www.uahirise.org/dtm/) de la universidad de Arizona. Corresponde a una porción de la superficie marciana. Por su tamaño, es necesario submuestrearla.

<p align="center">
  <img src="https://github.com/ShoyChoy/planeacion-ruta-a-marte/blob/main/mapa_marte.jpg" />
</p>

## Restricciones 

Un robot explorador como el Rover Perseverance no puede escalar o trepar, por lo que se considera que una superficie a la que puede desplazarse es una "plana", sin cambios bruscos de altura. Por ello, para cada pixel del mapa, se realizó lo siguiente:

* Se determinó la diferencia entre la altura del pixel y las alturas de sus ocho vecinos. 
* Si hay un solo pixel vecino para el cual la diferencia entre alturas es mayor a un metro, el pixel que se está probando ya no se considera aceptable para que navegue el robot.

Como resultado se obtuvo el siguiente mapa, donde el color negro representa el área transitable por el robot, y el blanco los obstáculos.

<p align="center">
  <img src="https://github.com/ShoyChoy/planeacion-ruta-a-marte/blob/main/zona%20navegable.jpg" />
</p>

## Resultados

Para el objetivo estático, de acuerdo con los experimentos detallados en [Planeacion de rutas.pdf](https://github.com/ShoyChoy/planeacion-ruta-a-marte/blob/main/Planeaci%C3%B3n%20de%20rutas.pdf) el algoritmo A* muestra ser eficiente para el trazado de rutas, consiguiendo respuestas efectivas en un tiempo aceptable. Por el otro lado, no ocurre lo mismo cuando el objetivo es móvil, donde se tuvo que submuestrear aún más la matriz que representa al mapa.



