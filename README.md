# Docker Desktop


Para esta actividad tuvimos que utilzar la aplicación Docker Desktop para tener un primer vistazo de la misma.

Se nos fue enviado unos ejercicios a realizar, los cuales estarán documentados a continuación:

## Paso 1:


EL primer paso se nos pidió descargar la imagen Alpine, la cual funciona como plantilla para los contenedores que vamos a crear más adelante.

Para esto, tenemos que abrir la terminal de la propia aplicación o, en caso de estar en Linux, abrir la propia terminal del sistema operativo, esta segunda opción no es obligatoria; ahora que estamos en la terminal, tenemo que introducir el código "docker pull alpine" para poder descargar la imagen sin arrancarla.

<img width="800" height="251" alt="Captura de pantalla 2025-10-06 161206" src="https://github.com/user-attachments/assets/6be036e3-70b2-4deb-999d-7bcd021d4dbc" />


<img width="800" height="624" alt="Captura de pantalla 2025-10-06 161632" src="https://github.com/user-attachments/assets/d35ad4e3-a3ac-42f3-92c8-e270e5d17844" />



## Paso 2:


Para seguir probando la aplicación, creamos un contenedor sin imagen, este contenedor tendrá el nombre de "hello-world" ya que permite que crear un contenedor que sirva como una pequeña introducción.


Para crear el contenedor, utilizaremos "docker run hello-world". El comando "run" es lo que nos permite crear el contenedor.


<img width="800" height="861" alt="Captura de pantalla 2025-10-06 161921" src="https://github.com/user-attachments/assets/17abd374-11aa-4156-9aa8-adc7b023fca7" />


<img width="800" height="583" alt="Captura de pantalla 2025-10-06 161944" src="https://github.com/user-attachments/assets/56c62cbf-0ec9-41d7-a9c4-d248a26d45ed" />


## Paso 3:

Ahora que ya tenemos la imagen, podemos crear nuestro primer contenedor con ella. Este contenedor, que llamaremos "damalp_1", lo crearemos usando "docker run -it --name=damalp_1 alpine /bin/sh". Este código está compuesto por el comando "run", "-i" hace que podamos interactuar con le contenedor, "-t" hace que podamos trabajar con el contenedor desde nuestra terminal sin tener que entrar al mismo, "name" que permite poner el nombre y "/bin/sh" nos permite entrar al contenedor una vez ejecutemos el código.


<img width="800" height="69" alt="Captura de pantalla 2025-10-06 162655" src="https://github.com/user-attachments/assets/299376f5-12cb-403e-b7a7-51c007406ca8" />


<img width="800" height="676" alt="Captura de pantalla 2025-10-06 164308" src="https://github.com/user-attachments/assets/25dc6e9a-a547-46c3-be2b-b2aa5a2fb748" />


En esta segunda imagen podemos ver que el contenedor ya estña en ejecución.


## Paso 4:

Ya teniendo el contenedor, vamos a entrar a el para ver si no está vacío.


<img width="800" height="1674" alt="Captura de pantalla 2025-10-06 164322" src="https://github.com/user-attachments/assets/a6e94705-b18f-4149-82a7-28f00d865feb" />


Como podemos ver, no está vacío.


Por otro lado, podemos ver que tenemos disponible la terminal del contenedor. Para esta actividad tenemos que buscar cual es la dirección IP del mismo y comprobar si se puede hacer ping a Google.


<img width="800" height="623" alt="Captura de pantalla 2025-10-06 164329" src="https://github.com/user-attachments/assets/702e2286-ece9-4d7b-92f7-64900aebe161" />


Para obtener la dirección IP solo tendremos que ejecutar "ip addr show eth0" y se nos mostrarán unas líneas de código. Aquí tenemos que buscar la línea que ponga "inet" y es ahí donde tendremos nuestra dirección IP.

<img width="800" height="701" alt="Captura de pantalla 2025-10-06 164347" src="https://github.com/user-attachments/assets/a8b789bd-85c0-406d-bdc7-75aa4164bc85" />


Por último, para comprobar si podemos hacer ping a Google, tenemos que introducir "ping -c 4 google.com" y verémos como hace lo que se nos pide. Es importante indicar las veces que queramos hacer ping a cualquier sitio ya que podemos desencadenar un bucle infinito de pings, es por eso que en el comando se escribe "-c 4" para definir el límite.


<img width="800" height="730" alt="Captura de pantalla 2025-10-06 164436" src="https://github.com/user-attachments/assets/2cddf6f9-49ba-43f6-9c72-2d8fd90b5fef" />


## Paso 5:

En este siguiente paso tenemos que crear otro contenedor con la misma imagen Alpine. Para esto utilizaremos es mismo código que usamos antes, o sea, "docker run -it --name=damalp_2 alpine /bin/sh". Este segundo contenedor se llamará "damalp_2", una vez dentro podemos ver que es igual al contenedor que creamos con la misma imagen.

Ya que creamos este segundo contenedor, se nos manda a comprobar si podemos hacer ping entre los dos contenedores. Para eso solo hay que hacer "ping damalp_1"


<img width="800" height="505" alt="Captura de pantalla 2025-10-06 170753" src="https://github.com/user-attachments/assets/b31736aa-a0ce-45f2-8692-206ca56c224a" />


Como se puede ver, al intentar hacer ping, nos da error. Para solucionar esto, tenemos que crear una red para realizar la conexión entre los dos contenedores. Con "docker network create red_dam" podemos crear esta red con el nombre "red_dam" y, para conectar los contenedores a la red, solo usaremos "docker network connect red_dam damalp_Nº".


<img width="800" height="186" alt="Captura de pantalla 2025-10-06 171614" src="https://github.com/user-attachments/assets/1ebd6f1e-98b6-4812-b588-8bd09d4fe99a" />

Ahora que está conectadas ya podremos hacer ping entre contenedores:


<img width="800" height="752" alt="Captura de pantalla 2025-10-06 171958" src="https://github.com/user-attachments/assets/bd8a0bf0-9099-4a5d-802d-ab21de95c171" />


## Paso 6:

Ahora, ¿qué pasa si cerramos las terminales de los contenedores?


En resumen, no pasa nada ya que los contenedores no dependen al 100% de la terminal.

<img width="800" height="1809" alt="Captura de pantalla 2025-10-06 183903" src="https://github.com/user-attachments/assets/2d9a6973-cca7-4298-9949-9452a39e0f35" />


## Paso 7: 


Ya que realizamos todas las tareas dentro de los contenedores, se quiere saber cuanta memoria RAM y cuanta memoria del disco duro utilizarón.

Para averiguar esto es muy sencillo ya que solo hay dos código que podemos usar.

**Memoria RAM:**
Con el código "docker stats" podemos ver cuanta memoria utilizan los contenedores en ejecución. Se puede apreciar en MEM USAGE y MEM%:

<img width="800" height="39" alt="Captura de pantalla 2025-10-06 172553" src="https://github.com/user-attachments/assets/b4c5822f-69ee-432e-82d9-e9bc43bdd250" />
<img width="800" height="135" alt="Captura de pantalla 2025-10-06 172601" src="https://github.com/user-attachments/assets/e8eef907-8969-4cdf-b37f-29a943b78982" />


**Memoria del disco duro**
Con "docker ps -a" podemos ver las características generales de los contenedores en ejecución. Para ver cuanto espacio ocupan tenemos que ver el final de la lista donde pone SIZE:


<img width="800" height="178" alt="Captura de pantalla 2025-10-06 172809" src="https://github.com/user-attachments/assets/65095dbb-666c-46de-a473-f523998a2f4d" />


# FIN





