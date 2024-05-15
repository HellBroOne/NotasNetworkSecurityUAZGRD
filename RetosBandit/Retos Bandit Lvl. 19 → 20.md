# Level 19
## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

Para obtener acceso al siguiente nivel, debe utilizar el binario setuid en el directorio de inicio. Ejecútelo sin argumentos para saber cómo usarlo. La contraseña para este nivel se puede encontrar en el lugar habitual (/etc/bandit_pass), después de haber utilizado el binario setuid.
### Datos de Acceso al nivel
Comandos: setuid
Usuario: bandit19
Contraseña:  *awhqfNnAbc1naukrpqDYcF95h7HoMTrC* (Nivel 19), *VxCazJaVykI6W36BkBU0mJTCM8rR95XT* (Nivel 20)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 19)
```
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rwsr-x---  1 bandit20 bandit19 14876 Oct  5 06:19 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit20@bandit.labs.overthewire.org -p 2220
Enter password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
### Notas Adicionales
Para este nivel se realizó una conexión desde un setuid, que básicamente permite personalizar los permisos para un archivo. Una definicion es: *Setuid y Setgid son términos de Unix, abreviaturas para "Set User ID" y "Set Group ID", respectivamente. Setuid, también llamado a veces "**suid**", y "**setgid**" son permisos de acceso que pueden asignarse a archivos o directorios en un sistema operativo basado en Unix.*
### Referencias
https://overthewire.org/wargames/bandit/bandit20.html