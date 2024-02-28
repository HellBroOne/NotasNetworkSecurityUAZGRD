# Level 25
## Objetivo
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

Iniciar sesión en bandit26 desde bandit25 debería ser bastante fácil... El shell para el usuario bandit26 no es **/bin/bash**, sino algo más. Descubre qué es, cómo funciona y cómo salir de él.
### Datos de Acceso al nivel
Comandos: ssh, cat, more, vi, ls, id, pwd
Usuario: bandit25
Contraseña:  *p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d* (Nivel 25), *c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1* (Nivel 26)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 25)
```
bandit25@bandit:~$ ls
bandit26.sshkey
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit25/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit25/.ssh/known_hosts).

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
 |_.__/ \__,_|_| |_|\__,_|_|\__|____\___/
Connection to localhost closed.
```
Lo que hacemos aquí es que se pueda ejecutar more haciendo chica la ventana y seguimos
```
[En More]
v
[En vim]
(tecla esc)
:set shell=/bin/bash
:sh
[salimos de vim]
[salimos de More]
bandit26@bandit:~$ 
```
**Rápido!, luego luego a hacer el reto 26 a 27.**
### Notas Adicionales
Para este nivel, el programa "more" nos estaba impidiendo el paso a la consola, la idea era hacer que, mediante una ssh acceder pero para ello, tuvimos que hacer que more se ejecutara antes de que nos sacara del bash. Por ello, la idea fue muy curiosa, al momento de acceder al servidor de bandit26 tuve que hacer chica la ventana de comandos, para así hacer que more se ejecutara. Y una vez dentro, con "v" ejecutar vim, para pasar al modo de comandos y hacer que pudiéramos acceder al shell

### Referencias
https://overthewire.org/wargames/bandit/bandit26.html