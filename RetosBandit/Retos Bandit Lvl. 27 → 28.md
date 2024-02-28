# Level 27
## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.
Clone the repository and find the password for the next level.

Hay un repositorio git en `ssh://bandit27-git@localhost/home/bandit27-git/repo` a través del puerto `2220`. La contraseña del usuario `bandit27-git` es la misma que la del usuario `bandit27`.
Clona el repositorio y busca la contraseña para el siguiente nivel.
### Datos de Acceso al nivel
Comandos: git
Usuario: bandit27
Contraseña: *YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS* (Nivel 27), *AVanL161y9rsbcJIsFHuw35rjaOM19nR* (Nivel 28)
Servidor: bandit.labs.overthewire.org 
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 27)
```
bandit27@bandit:~$ cd /tmp/hbro
bandit27@bandit:/tmp/hbro$ git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).

                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

!!! You are trying to log into this SSH server on port 22, which is not intended.

bandit27-git@localhost: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
bandit27@bandit:/tmp/hbro$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/hbro$ ls
bandit24.sh  pass  repo  y
bandit27@bandit:/tmp/hbro$ cd repo
bandit27@bandit:/tmp/hbro/repo$ ls
README
bandit27@bandit:/tmp/hbro/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/hbro/repo$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit28@bandit.labs.overthewire.org -p 2220
Enter password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
### Notas Adicionales
En este nivel se usó git, la idea fue clonar un repositorio a una carpeta propia y ya con el repo, obtener uno de los archivos del repositorio llamado README dónde pudimos verificar el password del siguiente nivel.
### Referencias
https://overthewire.org/wargames/bandit/bandit28.html