# Level 31
## Objetivo
After all this `git` stuff its time for another escape. Good luck!

Después de todo esto de `git`, es hora de escapar de nuevo. ¡Buena suerte!
### Datos de Acceso al nivel
Comandos: sh, man
Usuario: bandit32
Contraseña:  *rmCBvG56y58BXzv98yZGdO7ATVL5dW8y* (Nivel 32), *odHo63fHiFqcWWJG9rLiLDtPm45KzUKy* (Nivel 33)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 32)
```
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> $0
$ ls -al
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Oct  5 06:19 uppershell
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$ exit

C:\Users\gerar>ssh bandit33@bandit.labs.overthewire.org -p 2220
Enter password: odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```
### Notas Adicionales
Este nivel nos hizo entrar en una shell que solamente soportara mayúsculas, la idea de este nivel es acceder al shell, para ello hay que tratar de usar un comando para darnos cuenta que es imposible usar minusculas, con ello, hay que usar "$0" para entrar al shell y ver el archivo de los passwords
### Referencias
https://overthewire.org/wargames/bandit/bandit33.html