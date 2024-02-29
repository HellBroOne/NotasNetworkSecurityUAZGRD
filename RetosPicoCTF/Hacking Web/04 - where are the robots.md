## Descripcion
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

¿Puedes encontrar los robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([enlace](https://jupiter.challenges.picoctf.org/problem/36474/)) o http://jupiter.challenges. picoctf.org:36474
### Pistas
1. What part of the website could tell you where the creator doesn't want you to look?
### Solución
1. Hay que entrar al link de https://jupiter.challenges.picoctf.org/problem/36474/
2. Agregamos "robots.txt" al final del URL (https://jupiter.challenges.picoctf.org/problem/36474/robots.txt)
3. El segmento que diga en "disallow" es la pagina dónde no se debe entrar. (En este caso es "477ce.html")
4. Entramos a https://jupiter.challenges.picoctf.org/problem/36474//477ce.html.
### Notas Adicionales
El archivo *robots.txt* está en cualquier página, y sirve para gestionar el tráfico de rastreadores en una página.
### Referencias
https://play.picoctf.org/practice/challenge/4
https://jupiter.challenges.picoctf.org/problem/36474/
