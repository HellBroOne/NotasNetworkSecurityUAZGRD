# Level 14
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al **puerto 30000 en localhost.**
### Datos de Acceso al nivel
Comandos: ssh, telnet, nc, openssl, s_client, nmap
Usuario: bandit14
Contraseña: *fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq* (Nivel 14), *jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt* (Nivel 15)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 14)
```
bandit14@bandit:~$ echo "ola"
ola
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

^C
bandit14@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit15@bandit.labs.overthewire.org -p 2220
Enter password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
### Notas Adicionales
Para este nivel accedimos al local host mediante el puerto 30000, con este servidor, pudimos ingresar el password de este nivel para proseguir.
**nc:** (NetCat) Netcat es una herramienta de red que permite a través de intérprete de comandos y con una sintaxis sencilla abrir puertos TCP/UDP en un HOST (quedando netcat a la escucha), asociar una shell a un puerto en concreto (para conectarse por ejemplo a MS-DOS o al intérprete bash de Linux remotamente). "nc" nos permite conectarnos a varios puertos disponibles.
### Referencias
https://overthewire.org/wargames/bandit/bandit15.html