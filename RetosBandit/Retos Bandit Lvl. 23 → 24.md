# Level 23
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y ve qué comando se está ejecutando.
**NOTA:** Este nivel requiere que crees tu propio primer script de shell. ¡Este es un gran paso y deberías estar orgulloso de ti mismo cuando superes este nivel!
**NOTA 2:** Ten en cuenta que su script de shell se elimina una vez ejecutado, por lo que es posible que desees conservar una copia...
### Datos de Acceso al nivel
Comandos: cron, crontab, crontab(5) (use “man 5 crontab” to access this)
Usuario: bandit23
Contraseña: *QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G* (Nivel 23), *VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar* (Nivel 24)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 23)
```
bandit23@bandit:~$ cd /etc/cron.d/
bandit23@bandit:/etc/cron.d$ ls -la
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
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
bandit23@bandit:/etc/cron.d$ mkdir /tmp/hbro
bandit23@bandit:/etc/cron.d$ cd /tmp/hbro
bandit23@bandit:/tmp/hbro$ ls
bandit24.sh
bandit23@bandit:/tmp/hbro$ nano bandit24.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.
[EN NANO]
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/hbro/pass
[GUARDAR CTRL+O Y SALIR DE NANO]
bandit23@bandit:/tmp/hbro$ chmod 77 bandit24.sh
bandit23@bandit:/tmp/hbro$ chmod 777 bandit24.sh
bandit23@bandit:/tmp/hbro$ cp bandit24.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/hbro$ chmod 777 /tmp/hbro
bandit23@bandit:/tmp/hbro$ ls
bandit24.sh  pass
bandit23@bandit:/tmp/hbro$ cat pass
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/hbro$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit24@bandit.labs.overthewire.org -p 2220
Enter password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
### Notas Adicionales
En este nivel se usó cron, y crontab que son herramientas que nos sirven para administrar las tareas en tiempos. Una definición de Wikipedia que ayuda a entender esto es la siguiente:
"*En el sistema operativo Unix, **cron** es un administrador regular de procesos en segundo plano (demonio) que ejecuta procesos o guiones a intervalos regulares (por ejemplo, cada minuto, día, semana o mes). Los procesos que deben ejecutarse y la hora a la que deben hacerlo se especifican en el archivo 'crontab'. El nombre _cron_ proviene del griego 
**chronos** (χρόνος) que significa "tiempo".
**Cron** se puede definir como el equivalente a Tareas Programadas de Windows.
### Referencias
https://overthewire.org/wargames/bandit/bandit24.html