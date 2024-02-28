## Descripcion
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `6dee9772`
Additional details will be available after launching your challenge instance.

### Pistas
1. Finding a cheatsheet for bash would be really helpful!
### Solución
```
hellbroone-picoctf@webshell:~$ ls
README.txt
hellbroone-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
--2024-02-27 18:35:43--  https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                           100%[===================================================================================================>]      34  --.-KB/s    in 0s      

2024-02-27 18:35:43 (14.3 MB/s) - 'flag' saved [34/34]

hellbroone-picoctf@webshell:~$ ls
README.txt  flag
hellbroone-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
hellbroone-picoctf@webshell:~$ 
```
### Notas Adicionales
### Referencias