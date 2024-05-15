# Level 13
## Objetivo
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on.

La contraseña para el siguiente nivel se almacena en **/etc/bandit_pass/bandit14 y solo puede ser leída por el usuario bandit14.** Para este nivel, no obtienes la siguiente contraseña, pero obtienes una clave SSH privada que puede usarse para iniciar sesión en el siguiente nivel. **Nota:** localhost es un nombre de host que se refiere a la máquina en la que está trabajando.
### Datos de Acceso al nivel
Comandos: ssh, telnet, nc, openssl, s_client, nmap
Usuario: bandit13, bandit14
Contraseña: *fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq* 
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 13)
```
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit13/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit13/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!
...

bandit14@bandit:~$ ls
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit14@bandit.labs.overthewire.org -p 2220
Enter password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```
### Notas Adicionales
Para este nivel nos conectamos con ssh a otro servidor, con una ssh privada dada en el problema:
```
ssh -i sshkey.private bandit14@localhost -p 2220
```
Con este comando se nos permitió acceder al servidor del nivel 14, para poder buscar en el directorio necesario.
**ssh:** conecta a un servidor mediante ssh.
### Referencias
https://overthewire.org/wargames/bandit/bandit14.html