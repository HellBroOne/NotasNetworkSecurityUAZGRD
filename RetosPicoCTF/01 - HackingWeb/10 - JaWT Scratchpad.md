## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!

Hay un sitio web seguro en https://jupiter.challenges.picoctf.org/problem/54253/ (enlace) o http://jupiter.challenges.picoctf.org:54253. ¡Intenta ver si puedes iniciar sesión como administrador!
### Pistas
1. What is that cookie?
2. Have you heard of JWT?

1. ¿Qué es esa "cookie"?
2. ¿Has oído hablar de JWT?
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
