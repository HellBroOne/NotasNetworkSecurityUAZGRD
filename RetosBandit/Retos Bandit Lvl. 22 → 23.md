# Level 22
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busca en **/etc/cron.d/** la configuración y ve qué comando se está ejecutando.
**NOTA:** Ver scripts de shell escritos por otras personas es una habilidad muy útil. El script de este nivel se ha hecho intencionadamente fácil de leer. Si tiene problemas para entender lo que hace, intente ejecutarlo para ver la información de depuración que imprime.
### Datos de Acceso al nivel
Comandos: cron, crontab, crontab(5) (use “man 5 crontab” to access this)
Usuario: bandit22
Contraseña:  *WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff* (Nivel 22), *QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G* (Nivel 23)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 22)
```
bandit22@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Oct  5 06:19 .
drwxr-xr-x 70 root root 4096 Oct  5 06:20 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit22@bandit:~$ cd /etc/cron.d
bandit22@bandit:/etc/cron.d$ ls -la
total 56
drwxr-xr-x   2 root root  4096 Oct  5 06:20 .
drwxr-xr-x 106 root root 12288 Oct  5 06:20 ..
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root   122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:/etc/cron.d$ /usr/bin/cronjob_bandit23.sh
Copying passwordfile /etc/bandit_pass/bandit22 to /tmp/8169b67bd894ddbb4412f91573b38db3
bandit22@bandit:/etc/cron.d$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:/etc/cron.d$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit23@bandit.labs.overthewire.org -p 2220

C:\Users\gerar>ssh bandit23@bandit.labs.overthewire.org -p 2220
Enter password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
### Notas Adicionales
En este nivel se usó cron, y crontab que son herramientas que nos sirven para administrar las tareas en tiempos. Una definición de Wikipedia que ayuda a entender esto es la siguiente:
"*En el sistema operativo Unix, **cron** es un administrador regular de procesos en segundo plano (demonio) que ejecuta procesos o guiones a intervalos regulares (por ejemplo, cada minuto, día, semana o mes). Los procesos que deben ejecutarse y la hora a la que deben hacerlo se especifican en el archivo 'crontab'. El nombre _cron_ proviene del griego 
**chronos:** (χρόνος) que significa "tiempo".
**Cron** se puede definir como el equivalente a Tareas Programadas de Windows.
### Referencias
https://overthewire.org/wargames/bandit/bandit23.html