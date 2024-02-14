# Level 1
## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

La contraseña para el siguiente nivel se almacena en un archivo llamado **readme** ubicado en el directorio de inicio. Utilice esta contraseña para iniciar sesión en bandit1 mediante SSH. Siempre que encuentres una contraseña para un nivel, usa SSH (en el puerto 2220) para iniciar sesión en ese nivel y continuar el juego.
### Datos de Acceso al nivel
Comandos: ls, cat
Usuario: bandit0
Contraseña: *NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 0)
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$ exit
logout
Connection to bandit.labs.overthewire closed.

C:Users/User> ssh bandit1@bandit.labs.overthewire.org -p 2220
Enter password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
### Notas Adicionales
El nivel 1 implementa lo básico de la terminal de Linux, como lo es el **ls para ver lo que hay en un directorio** y el **cat para poder leer** un archivo.
**ls**: mostrar contenido de un directorio.
**cat**: concatena y muestra archivos
### Referencias
https://overthewire.org/wargames/bandit/bandit1.html