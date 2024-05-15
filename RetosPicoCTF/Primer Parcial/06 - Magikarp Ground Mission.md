## Descripción
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `6dee9772`
Additional details will be available after launching your challenge instance.

¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicia el contenedor, "ssh" y luego "ls" una vez conectado para comenzar. Inicia sesión a través de `ssh` como `ctf-player` con la contraseña, `6dee9772`
Detalles adicionales estarán disponibles después de lanzar tu instancia de desafío.
### Pistas
1. Finding a cheatsheet for bash would be really helpful!
### Solución
```
hellbroone-picoctf@webshell:~$ ssh ctf-player@venus.picoctf.net -p 54819
The authenticity of host '[venus.picoctf.net]:54819 ([3.131.124.143]:54819)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:54819' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_ <<<< (BANDERA 1/3)
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ ls /
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt
cat: 2of3.flag.txt: No such file or directory
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ ls -la
total 92
drwxr-xr-x   1 root root 4096 Mar  1 05:02 .
drwxr-xr-x   1 root root 4096 Mar  1 05:02 ..
-rwxr-xr-x   1 root root    0 Mar  1 05:02 .dockerenv
-rw-r--r--   1 root root   17 Mar 16  2021 2of3.flag.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  340 Mar  1 05:02 dev
drwxr-xr-x   1 root root 4096 Mar  1 05:02 etc
drwxr-xr-x   1 root root 4096 Mar 16  2021 home
-rw-r--r--   1 root root   51 Mar 16  2021 instructions-to-3of3.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 lib
drwxr-xr-x   2 root root 4096 Feb 22  2021 lib64
drwxr-xr-x   2 root root 4096 Feb 22  2021 media
drwxr-xr-x   2 root root 4096 Feb 22  2021 mnt
drwxr-xr-x   1 root root 4096 Mar 16  2021 opt
dr-xr-xr-x 193 root root    0 Mar  1 05:02 proc
drwx------   2 root root 4096 Feb 22  2021 root
drwxr-xr-x   1 root root 4096 Mar  1 05:03 run
drwxr-xr-x   1 root root 4096 Mar 16  2021 sbin
drwxr-xr-x   2 root root 4096 Feb 22  2021 srv
dr-xr-xr-x  13 root root    0 Mar  1 05:02 sys
drwxrwxrwt   1 root root 4096 Mar 16  2021 tmp
drwxr-xr-x   1 root root 4096 Feb 22  2021 usr
drwxr-xr-x   1 root root 4096 Feb 22  2021 var
ctf-player@pico-chall$ cat "2of3.flag.txt"
0ut_0f_\/\/4t3r_ <<<< (BANDERA 2/3)
ctf-player@pico-chall$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls -la
total 32
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar  1 05:03 .
drwxr-xr-x 1 root       root       4096 Mar 16  2021 ..
drwx------ 2 ctf-player ctf-player 4096 Mar  1 05:03 .cache
-rw-r--r-- 1 ctf-player ctf-player   80 Mar 16  2021 .profile
drw------- 1 ctf-player ctf-player 4096 Mar 16  2021 .ssh
-rw-r--r-- 1 ctf-player ctf-player   10 Mar 16  2021 3of3.flag.txt
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 drop-in
ctf-player@pico-chall$ cat "3of3.flag.txt"
540e4e79} <<<< (BANDERA 3/3)
ctf-player@pico-chall$ exit
logout
Connection to venus.picoctf.net closed.
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended. 
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/189