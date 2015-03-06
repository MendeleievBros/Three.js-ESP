============================
Movimiento
============================

Ya tenemos la escena, y un objeto. Ahora toca hacer que se mueva el cubo.

Creamos la función animarEscena()
-------------------

Primero añadiremos una función, que se ejecutará cada pocas milésimas de segundo, en la que indicaremos que nuestro cubo rote.

Tenemos que añadir la variable cubo al principio del archivo javascript.js, para poder utilizarlo en cualquier parte de nuestro código.
Antes de la función startEscena(), pondremos esta función:

.. code-block:: javascript

   window.requestAnimFrame = (  
	function(){
		return  window.requestAnimationFrame       ||
		window.webkitRequestAnimationFrame ||
		window.mozRequestAnimationFrame    ||
		function( callback ){
			window.setTimeout(callback, 1000 / 60);
		};
   }
   )();

  
Con esta función, conseguiremos que se ejecute la función animarEscena() ciclicamente.

.. code-block:: javascript


   function animarEscena(){
	   requestAnimFrame(animarEscena); // para ejecutar ciclicamente

	   cubo.rotation.y+= 0.002; // rotamos el cubo en el eje y 0.002 unidades de medida.

       renderEscena();
   }	


Solo nos falta añadir a la función webGLStart() una llamada a nuestra nueva función.

Tiene que quedar así:

.. code-block:: javascript

   var escena;
   var camara;
   var render;
   var cubo;

   window.requestAnimFrame = ( 
	function(){
		return  window.requestAnimationFrame       ||
		window.webkitRequestAnimationFrame ||
		window.mozRequestAnimationFrame    ||
		function( callback ){
			window.setTimeout(callback, 1000 / 60);
		};
   }
   )();

   function animarEscena(){
	   requestAnimFrame(animarEscena); // para ejecutar ciclicamente

	   cubo.rotation.y+= 0.02; // rotamos el cubo en el eje y 0.02 unidades de medida.

       renderEscena();
   }	


   function startEscena(){
     //Render
     render = new THREE.WebGLRenderer(); // definimos el renderizador

     render.setClearColor(0x000000, 1); // el colorde limpieza, negro

     var canvasWidth = 500; // tamaño del canvas
     var canvasHeight = 500; // tamaño del canvas
     render.setSize(canvasWidth, canvasHeight);

     document.getElementById("canvas").appendChild(render.domElement); // indicamos que el render pinte la escena en el div canvas

     //Escena
     escena = new THREE.Scene(); // definimos la escena

     //Camara
     camara = new THREE.PerspectiveCamera(45, canvasWidth / canvasHeight, 0.2, 150); // definimos la camara
     camara.position.set(0, 0, 0); // situamos la cámara en las coordenadas absolutas
     camara.lookAt(escena.position); // le indicamos a la cámara que mire al centro de la escena.
     escena.add(camara); // añadimos la cámara a la escena

     //cubo
        var cuboMateriales = [
      new THREE.MeshBasicMaterial({color:0x33FF00}),
      new THREE.MeshBasicMaterial({color:0x00CCFF}),
      new THREE.MeshBasicMaterial({color:0xFF0000}),
      new THREE.MeshBasicMaterial({color:0xFFCC00}),
      new THREE.MeshBasicMaterial({color:0x99FFFF}),
      new THREE.MeshBasicMaterial({color:0xFFFFFF})
   ];
   var cuboMaterial = new THREE.MeshFaceMaterial(cuboMateriales);
   
   
   var cuboGeometria = new THREE.BoxGeometry(2, 2, 2);

   cubo = new THREE.Mesh(cuboGeometria, cuboMaterial);
   cubo.position.set(0, 0, -7.0);
   escena.add(cubo);


    
   }
   function renderEscena(){
     render.render(escena, camara); // para dibujar la escena
   }

   function webGLStart() { //función llamada cuando se carga la página (onload)
      startEscena();
      animarEscena();
      renderEscena();
   }
   

Resultado
---------
Si abrimos el archivo index.html en el navegador, veremos como el cubo rota:

.. figure:: img/escena_rotar.png


