============================
Tutorial de Three.js
============================
Tutorial en español que explica como utilizar la libreria Three.js.

----

============================
Preparando el terreno
============================
Para poder utilizar Javascript o cualquiera de sus librerías, no necesitamos instalar nada, pero si habilitar 
en el navegador la utilización de WebGL.


* Google Chrome


* * <b>Paso 1:</b> Abre el navegador y en la barra de direcciones escribe: chrome://flags/<br>

* * <b>Paso 2:</b> Desde esta página podemos habilitar soporte adicional al navegador web, en nuestro caso para WebGL, necesitas habilitar los siguientes experimentos:<br>

* * * WebGL (Importante)
* * * Ignorar la lista de renderización por software (Opcional si no funciona con el primero)
* * * Canvas 2D acelerado por GPU (opcional)<br>
* * <b>Paso 3:</b> Reinicia el navegador.
<br>




* Firefox

* * <b>Paso 1:</b> Abre el navegador y en la barra de direcciones escribe: about:config<br>

* * <b>Paso 2:</b> Desde esta página podemos habilitar soporte adicional al navegador web, en nuestro caso para WebGL, necesitas habilitar los siguientes experimentos:<br>

* * * webgl.force-enabled. (importante)
* * * layers.acceleration.force-enabled --> solo en windows
* * * gfx.direct2d.force-enabled --> solo en windows <br>
* * <b>Paso 3:</b> Reinicia el navegador.
<br>


Una vez habilitado, abre esta página. <a href="http://get.webgl.org/">get.webgl.org</a> , te debería salir algo así:<br>
<img src="img/webgl_chrome.png"> 
