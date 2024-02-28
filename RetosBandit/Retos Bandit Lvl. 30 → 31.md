# Level 30
## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Hay un repositorio git en `ssh://bandit30-git@localhost/home/bandit30-git/repo` a través del puerto `2220`. La contraseña del usuario `bandit30-git` es la misma que la del usuario `bandit30`.
### Datos de Acceso al nivel
Comandos: git
Usuario: bandit30
Contraseña:  *xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS* (Nivel 30), *OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt* (Nivel 31)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 30)
```
bandit30@bandit:~$ mkdir /tmp/lorord
bandit30@bandit:~$ cd /tmp/lorord
bandit30@bandit:/tmp/lorord$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/lorord$ cd repo
bandit30@bandit:/tmp/lorord/repo$ ls
README.md
bandit30@bandit:/tmp/lorord/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/lorord/repo$ git tag
secret
bandit30@bandit:/tmp/lorord/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/lorord/repo$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit31@bandit.labs.overthewire.org -p 2220
Enter password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```
### Notas Adicionales
En este nivel se usaron las etiquetas de git, y haciendo uso de show secret para ver los caracteres ocultos de un archivo.
### Referencias
https://overthewire.org/wargames/bandit/bandit31.html