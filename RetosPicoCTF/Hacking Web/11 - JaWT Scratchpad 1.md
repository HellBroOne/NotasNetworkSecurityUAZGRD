## Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

Encuentra la bandera que se mantiene en este servidor para adelantarte a la competencia [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)
### Pistas
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses

1. Quizás tengas más de 2 opciones
2. Consulte herramientas como Burpsuite para modificar sus solicitudes y observar las respuestas.
### Solución
1. Para esto hay que obtener la cookie del JWT que genera.
2. Esto lo podemos "desglosar" con la página de jwt.io, para ver el JSON del jwt
3. La palabra clave debe ser cambiada a "ilovepico" para poder obtener un nuevo JWT.
4. Ahora cambiamos el valor de esa cookie por el nuevo jwt que obtuvimos.
5. Se nos dará ahora la bandera.
### Notas Adicionales
Para este reto aprendimos a utilizar las jwt para poder modificar valores, las jwt son piezas de código comprimido por así decirlo, sirve para 
### Referencias
https://play.picoctf.org/practice/challenge/8
http://jupiter.challenges.picoctf.org:54253
