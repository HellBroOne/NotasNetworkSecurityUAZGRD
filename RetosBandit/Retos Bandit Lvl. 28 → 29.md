# Level 28
## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Hay un repositorio git en `ssh://bandit28-git@localhost/home/bandit28-git/repo` a través del puerto `2220`. La contraseña del usuario `bandit28-git` es la misma que la del usuario `bandit28`.

### Datos de Acceso al nivel
Comandos: git
Usuario: bandit28
Contraseña: *AVanL161y9rsbcJIsFHuw35rjaOM19nR* (Nivel 28), *tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S* (Nivel 29)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 28)
```
bandit28@bandit:/tmp/hbro$ cd /tmp/hbroone
bandit28@bandit:/tmp/hbroone$ cd
bandit28@bandit:~$ cd /tmp/hbroone
bandit28@bandit:/tmp/hbroone$ ls
bandit24.sh
bandit28@bandit:/tmp/hbroone$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/hbroone$ ls
bandit24.sh  repo
bandit28@bandit:/tmp/hbroone$ cd ./repo
bandit28@bandit:/tmp/hbroone/repo$ ls
README.md
bandit28@bandit:/tmp/hbroone/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/hbroone/repo$ git log
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

commit f08b9cc63fa1a4602fb065257633c2dae6e5651b
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    add missing data

commit a645bcc508c63f081234911d2f631f87cf469258
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    initial commit of README.md
bandit28@bandit:/tmp/hbroone/repo$ git show
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx

bandit28@bandit:/tmp/hbroone/repo$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit29@bandit.labs.overthewire.org -p 2220
Enter password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
### Notas Adicionales
En este nivel se usó git de nuevo, y con el uso del log y show pudimos ver los detalles ocultos de un archivo.
### Referencias
https://overthewire.org/wargames/bandit/bandit29.html