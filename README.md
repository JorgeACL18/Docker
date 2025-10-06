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

Ahora que ya tenemos la imagen, podemos crear nuestro primer contenedor con ella. Este contenedor, que llamaremos "damalp_1", lo crearemos usando "docker run -it --name=damaalp_1 alpine /bin/sh". Este código está compuesto por el comando "run", "-i" hace que podamos interactuar con le contenedor, "-t" hace que podamos trabajar con el contenedor desde nuestra terminal sin tener que entrar al mismo, "name" que permite poner el nombre y "/bin/sh" nos permite entrar al contenedor una vez ejecutemos el código.


<img width="800" height="69" alt="Captura de pantalla 2025-10-06 162655" src="https://github.com/user-attachments/assets/299376f5-12cb-403e-b7a7-51c007406ca8" />


<img width="800" height="676" alt="Captura de pantalla 2025-10-06 164308" src="https://github.com/user-attachments/assets/25dc6e9a-a547-46c3-be2b-b2aa5a2fb748" />


En esta segunda imagen podemos ver que el contenedor ya estña en ejecución.
