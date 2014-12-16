
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

Estará en el archivo javascript.js, está dentro de la carpeta js.


.. code-block:: javascript

   var escena;
   var camara;
   var render;

   function iniciarEscena(){
     //Render
     render = new THREE.WebGLRenderer();

     render.setClearColorHex(0x000000, 1);

     var canvasWidth = 500;
     var canvasHeight = 500;
     render.setSize(canvasWidth, canvasHeight);

     document.getElementById("canvas").appendChild(render.domElement);

     //Escena
     escena = new THREE.Scene();

     //Camara
     camara = new THREE.PerspectiveCamera(45, canvasWidth / canvasHeight, 0.1, 100);
     camara.position.set(0, 0, 0);
     camara.lookAt(escena.position);
     escena.add(camara);

    
   }
   function renderEscena(){
     render.render(escena, camara);
   }

   function webGLStart() {
      iniciarEscena();
      renderEscena();
   }

