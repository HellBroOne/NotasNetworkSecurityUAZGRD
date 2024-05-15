## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

Encuentra la bandera que se mantiene en este servidor para adelantarte a la competencia [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)
### Pistas
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses.

1. Quizás tengas más de 2 opciones
2. Consulte herramientas como Burpsuite para modificar sus solicitudes y observar las respuestas.
### Solución
1. Para esto hay que entrar al sitio web del reto. 
2. Podremos ver que con el botón *Red* se hace una petición con el método GET y con el botón *Blue* se hace una petición del método POST.
3. Podremos editar este método abriendo "Inspeccionar" e ir al apartado de RED/NETWORK.
4. Presionamos cualquier botón y vemos que se hace una solicitud en el archivo "index.js" 
5. Hacemos clic derecho y vamos a la sección de "Editar y volver a Enviar".
6. Se cambia el método actual por el método *HEAD*.
7. Se nos dará ahora la bandera en la sección de *"Flag"*. (" picoCTF{r3j3ct_th3_du4l1ty_70bc61c4} ")
### Notas Adicionales
En este reto aprendimos sobre el uso de los proxies y los métodos de encabezado, estos métodos nos sirven para poder obtener varios tipos de información mediante diferentes métodos, por ejemplo:
1. **GET**: Como su nombre lo indica, este método obtiene la información necesaria sin hacer nada más.
2. **POST**: Este método envía una solicitud de la información y se obtiene despúes de esa respuesta.
3. **HEAD**: Este método es una respuesta de encabezado sin cuerpo de la respuesta, sirve para mandar los encabezados.
### Referencias
https://play.picoctf.org/practice/challenge/132
[http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)
