# Level 31
## Objetivo
There is a git repository at `ssh://bandit31-git@localhost:2220/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Hay un repositorio git en `ssh://bandit31-git@localhost/home/bandit31-git/repo` a través del puerto `2220`. La contraseña del usuario `bandit31-git` es la misma que la del usuario `bandit31`.
### Datos de Acceso al nivel
Comandos: git
Usuario: bandit31
Contraseña: *OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt* (Nivel 31), *rmCBvG56y58BXzv98yZGdO7ATVL5dW8y* (Nivel 32)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 31)
```
bandit31@bandit:~$ mkdir /tmp/elpepe
bandit31@bandit:~$ cd/tmp/elpepe
-bash: cd/tmp/elpepe: No such file or directory
bandit31@bandit:~$ cd /tmp/elpepe
bandit31@bandit:/tmp/elpepe$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit31@bandit:/tmp/elpepe$ ls
repo
bandit31@bandit:/tmp/elpepe$ cd repo
bandit31@bandit:/tmp/elpepe/repo$ ls
README.md
bandit31@bandit:/tmp/elpepe/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/elpepe/repo$ nano key.txt
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit31@bandit:/tmp/elpepe/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/elpepe/repo$ git add -f key.txt
bandit31@bandit:/tmp/elpepe/repo$ git commit -m "comm"
[master e700bb2] comm
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/elpepe/repo$ git push origin
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 316 bytes | 316.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/elpepe/repo$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit32@bandit.labs.overthewire.org -p 2220
Enter password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```
### Notas Adicionales
En este nivel se usó *git add, git commit*, para poder hacer que se suba un archivo a un repositorio, la idea simplemente era hacer un push de un archivo hacia el repo para tener la nueva contraseña.
### Referencias
https://overthewire.org/wargames/bandit/bandit32.html