============================
Conceptos básicos
============================

Empecemos a diseñar nuestro proyecto

Que vamos a hacer
-----------------

Para este tutorial haremos un proyecto en el cual aparecerá un cubo que podremos mover por la escena.

Partes del proyecto
-------------------
Vamos a desgranar el proyecto en diferentes objetos, explicando cada uno:

- **Canvas** --> Canvas (lienzo en inglés) es un elemento HTML que permite la generación de gráficos dinámicamente. El objeto canvas puede ser accedido a través de JavaScript, permitiendo generar gráficos 2D, juegos, animaciones y composición de imágenes.

- **Escena** --> Una escena es un espacio tridimensional en el que puedes añadir               objetos, interactuar con ellos y moverte por el.

- **Render** --> Un render es el objeto WebGL donde la tarjeta gráfica pintará todos los gráficos. Un mundo 3D (escena) puede ser enorme, pero en pantalla sólo se pintará aquello que quede dentro del encuadre de la “cámara”. Ésto es lo que llamaremos render.

- **Camara** --> Una escena puede contener tantas cámaras como deseemos, pero sólo se podrá utilizar una de ellas para renderizar la escena en un momento dado. Una cámara puede ser posicionada y rotada tantas veces como queramos.Para definir una cámara hay que tener en cuenta qué tipo de proyección queremos tener. Three.js nos proporciona tres tipos de proyecciones:
   - Proyección paralela, cámara del tipo OrthographicCamera
   - Proyección cónica, cámara del tipo PerspectiveCamera
   - Proyección combinada, cámara del tipo CombinedCamera, y que permite cambiar entre la proyección cónica y paralela en tiempo de ejecución.

 La OrthographicCamera es una perspectiva que respeta el tamaño de los objetos, independientemente de la distancia a la que se encuentren de la cámara.

 La PerspectiveCamera es la que deforma los objetos según la distancia y posición que se encuentren con respecto a la cámara, tal y como ocurre en el mundo real.

- **Figura** --> Una figura es la cosa que quieres pintar en la pantalla. Un punto, Una línea, un triángulo, Un cuadrado. Un cubo. Un coche. Three.js llama a este tipo de objeto como Mesh.

 Para crear una figura, Three.js necesita dos cosas: Una geometría y un material.

   - La **geometría** es la lista de vértices y caras que forman una figura determinada. Three.js permite crear geometrías de muy diversas formas, como puedes encontrar en su documentación. Hay clases para definir figuras vértice a vértice, a mano, pero también hay clases que nos dibujan cubos, esferas o conos.

   - Los **materiales** son “la piel” de las figuras, sirven para definir de qué color es cada cara de una figura y cómo la luz actúa en dicha cara. Al igual que con las geometrías, Three.js nos proporciona un montón de clases para crear distintos tipos de materiales según el efecto que queramos tener.
