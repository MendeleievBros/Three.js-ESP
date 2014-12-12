
============================
Creando una escena
============================

Separaremos la parte estética, que contiene el canvas con la parte lógica que contendrá la manipulación del cubo.

Parte estética
--------------

Estará en el archivo index.html, y será el archivo "ejecutable".


.. code-block:: html

    <!DOCTYPE html>
    <html>
    <head>
    <title>Cubo three.js</title>
    <meta http-equiv="content-type" content="text/html; charset=utf-8">
    <script src="js/three.min.js"></script> 
    <script src="js/javascript.js"></script> // archivo que contendrá la parte lógica
    </head>
    <body onload="webGLStart();">
    <div id="canvas"></div>
    </body>
    </html>


Parte lógica
--------------

Estará en el archivo javascript.js, está dentro de la carpeta javascript..


.. code-block:: html

    <!DOCTYPE html>
    <html>
    <head>
    <title>Cubo three.js</title>
    <meta http-equiv="content-type" content="text/html; charset=utf-8">
    <script src="js/three.min.js"></script> 
    <script src="js/javascript.js"></script> // archivo que contendrá la parte lógica
    </head>
    <body onload="webGLStart();">
    <div id="canvas"></div>
    </body>
    </html>

