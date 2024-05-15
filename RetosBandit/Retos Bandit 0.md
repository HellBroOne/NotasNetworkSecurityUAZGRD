# Level 0
## Objetivo
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) page to find out how to beat Level 1.

El objetivo de este nivel es que accedas al juego usando SSH. El servidor al cual te tienes que conectar es **bandit.labs.overthewire.org**, en el puerto 2220. El nombre de usuario es **bandit0** y la contraseña es **bandit0**. Una vez con la sesión iniciada, ve a la página del [Nivel 1](https://overthewire.org/wargames/bandit/bandit1.html) para buscar cómo vencer el Nivel 1.
### Datos de Acceso al nivel
Elementos: SSH
Usuario: Bandit0
Contraseña: Bandit0
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
```
C:users/User> ssh bandit0@bandit.labs.overthewire.org -p 2220
hostkeys_find_by_key_hostfile: hostkeys_foreach failed for C:\\Users\\gerar/.ssh/known_hosts: Permission denied
The authenticity of host '[bandit.labs.overthewire.org]:2220 ([51.20.13.48]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Failed to add the host to the list of known hosts (C:\\Users\\gerar/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
```
### Notas Adicionales
Este Nivel nos ayuda a poder comprender como acceder a los niveles de la plataforma de bandit, nos sirve al momento de querer acceder a nuevos niveles así como usar los ssh para acceder al servidor de bandit.
.
### Referencias
https://overthewire.org/wargames/bandit/bandit0.html

