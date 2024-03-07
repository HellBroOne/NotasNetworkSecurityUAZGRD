## Descripcion
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!

Hay un sitio web seguro en https://jupiter.challenges.picoctf.org/problem/54253/ (enlace) o http://jupiter.challenges.picoctf.org:54253. ¡Intenta ver si puedes iniciar sesión como administrador!
### Pistas
1. Seems like the password is encrypted.

1. Parece que la contraseña está cifrada.
### Solución
1. Viendo en la página del reto, se puede observar en la parte de "Support" que hay gente diciendo que obtiene un SQL Error, por ende, podemos deducir que esta página usa SQL.
2. Vamos al "Admin Login" y escribimos como la contraseña a lo que sea.
3. Cambiamos el campo attribute y value del campo de "debug" a show y con valor a 1
4. Damos Login y podemos ver que esta contraseña está encriptada. Tal parece que usa ROT13. 
5. Con CyberChef escribimos "' OR 1=1" para encriptarlo a ROT13 y obtenemos "' BE 1=1--"
6. Lo que esto hace es una inyección pero encriptada a ROT13, al saber que BE es lo mismo que OR entonces es posible hacer una inyección para obtener un valor true y poder entrar al sistema.
```
password: ' BE 1=1--
SQL query: SELECT * FROM admin where password = '' OR 1=1--'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}
```
### Notas Adicionales
Para este reto aprendimos a hacer inyecciones a una base de datos desde los campos del sitio, para ello hay que hacer consultas que ya sabemos hacer desde una base de datos.
### Referencias
https://play.picoctf.org/practice/challenge/8
http://jupiter.challenges.picoctf.org:54253
