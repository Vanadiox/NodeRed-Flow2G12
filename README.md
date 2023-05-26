# NodeRed-Flow2G12 24/May/23

En esta práctica se realizará el segundo ejercicio de nodos utilizando NodeRed. 

## Requisitos

1. Haber realizado y comprendido el [ejercicio anterior](https://github.com/Vanadiox/NodeRed-Flow2G12)

2. Al igual que el ejercicio anterior, se debe contar con una máquina virtual con Linux. En este caso se utilizó Ubuntu 22.04, Docker y Docker compose, al igual que tener instada las imágenes de NodeRed

##Instrucciones. 

En esta ocasión se va a trabajar sobre el trabajo _Flow 1_. Para ello vaya al menú de hamburguesa que se encuentra en la parte superior derecha de la pantalla y seleccione _export_.

![Imagen 1]()

Una vez abierta la ventana, usted debe de estar en la pestaña de _Current Flow_. Si ya está ahí, vaya a la pestaña _JSON_ que se encuentra un poco más abajo de _Current Flow._ Una vez ahí, aparecerá una serie de caracteres. Si se fija, en la parte superior del botón _Copy to Clipboard_ verá dos botoncitos: _compact y formatted_. Haga clic sobre _formated_ y el texto se verá un poco más ordenado. Hecho esto, de clic en "download" y en automático comenzará la descarga del archivo .json

![Imagen 2]()

Una vez descargado el archivo, es hora de importar ese .json a NodeRed para continuar. De nuevo, seleccione el menú hamburguesa y seleccione _import_. Se abrirá una ventana nueva. Cargue ahí el .json que se le descargo, utilizando el botón _select file to import_. Seleccione _Import to: new flow_ y de clic en _Import_

![Imagen 3]()

Aparecerá un cuadro haciéndonos saber que ya hay algunos nodos que ya existen (de los de la actividad anterior), también nos pregunta qué deseamos hacer. En este caso, hay que aceptar para poder continuar

![Imagen 4]()

Nos aparecerán los nodos que hicimos en la actividad anterior. Borraremos el enlace que une _timestamp_ y _debug 1_ darle clic a la unión, esta se coloreará de naranja y es aquí donde borramos con la tecla _suprimir_ o _supr_

![Imagen 5]()

Ahora es momento de agregar un nuevo nodo: _function_. Valga la redundancia, _function_ añade funcionalidades a nuestro _flow_, utilizando una sintáxis similar a Java Script. Para hacerlo, hay que ir a la columna en la izquierda y en la barra de búsqueda teclear "function". Aparecerá un cuadro que tiene la siguiente forma:

![Imagen 6]()

Arrastramos el nodo y lo unimos de la siguiente manera:

![Imagen 7]()

Damos doble clic al objeto function y aparecerá algo como esto:

![Imagen 8]()

Nos quedamos en la pestaña de _On Message_ y añadimos el siguiente código:

~~~
// Lo que está después de "//" son comentarios
// Crea un objeto Date a partir del msg.payload enviado por timestamp
var date = new Date(msg.payload);
// Cambia el payload para que sea una fecha con formato
msg.payload = date.toString();
//msg.payload = msg.payload = Date.UTC.toString();
// Regresa el mensaje para que se envíe al siguiente nodo
~~~

Quedará así:

![Imagen 9]()

Una vez añadido el texto y que el cuadro de incersión de texto no arroje errores, de clic en _Done_, luego en _Deploy_ y diríjase a la pestaña del bicho, mejor conocida como _Debug Messages_

Debería aparecer algo como esto:

![Imagen 10]()

Al final, quedaría todo el trabajo así: 

![Imagen 11]()

# Pero ¿No debimos configurar los nodos anteriores?

Y la respuesta es que no, debido a que los importamos desde el proyecto anterior. 

## ¿Y cómo detengo esto?

Puede hacer [esto](https://github.com/Vanadiox/NodeRed-Flow1G12) (yendo a la sección de "Detener el proyecto") o lo siguiente:

En el nodo _debug_, a la derecha tiene un cuadrito del mismo color que el nodo. Haga clic y se verá así:

![Imagen 12]()

Puede, opcionalmente dar clic en _Deploy_

Compare:

![Imagen 13]()

# ¡Y LISTO!

## Referencias:

[Código IoT: Servidor básico con Docker Compose](https://github.com/codigo-iot/servidor-IoT-basico-docker-compose)

[NodeRed-Flow1G12 -- 23/MAY/23](https://github.com/Vanadiox/NodeRed-Flow1G12)

## Créditos: 

[Manual realizado por Vanadiox (Kevin H)](https://github.com/Vanadiox)

[Referencias por Código IoT](https://github.com/codigo-iot)

