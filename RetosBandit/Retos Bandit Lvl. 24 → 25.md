# Level 24
## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le da la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN excepto revisando todas las 10000 combinaciones, lo que se denomina fuerza bruta.
No es necesario crear nuevas conexiones cada vez.
### Datos de Acceso al nivel
Comandos: [None]
Usuario: bandit24
Contraseña: *VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar* (Nivel 24), *p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d* (Nivel 25)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 24)
```
bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Timeout. Exiting.
mkdir /tmp/jagger
bandit24@bandit:~$ mkdir /tmp/jagger
bandit24@bandit:~$ cd /tmp/jagger
bandit24@bandit:/tmp/jagger$ nano bruteforce.sh
Unable to create directory /home/bandit24/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.
[EN NANO]
#!/bin/bash
passwd="VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar"
for i in {8000..9999}
do
        echo $passwd' '$i >> salida.txt
done
[GUARDAR Y SALIR DE NANO]
bandit24@bandit:/tmp/jagger$ chmod 777 bruteforce.sh
bandit24@bandit:/tmp/jagger$ ./bruteforce.sh
bandit24@bandit:/tmp/jagger$ cat salida.txt | nc localhost 30002 >> resultado.txt
bandit24@bandit:/tmp/jagger$ sort resultado.txt | uniq -u
Correct!
Exiting.
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
Timeout. Exiting.

C:\Users\gerar>ssh bandit25@bandit.labs.overthewire.org -p 2220
Enter password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```
### Notas Adicionales
En este nivel se usó el scripting, el cuál es una manera de crear scripts y ejecutar las instrucciones de un proceso que queramos ejecutar, la idea de este script es el de hacer "bruteforce" para adivinar de manera bruta cuál es el password, guiada por una sintaxis simple. 
### Referencias
https://overthewire.org/wargames/bandit/bandit25.html