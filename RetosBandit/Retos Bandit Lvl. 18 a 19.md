# Level 18
## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

La contraseña para el siguiente nivel se almacena en un archivo **readme** en el directorio de inicio. Desafortunadamente, alguien ha modificado **.bashrc** para cerrar tu sesión cuando inicias sesión con SSH.
### Datos de Acceso al nivel
Comandos: ssh, ls, cat
Usuario: bandit18
Contraseña: *hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg* (Nivel 18), *awhqfNnAbc1naukrpqDYcF95h7HoMTrC* (Nivel 19)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 18)
```
C:\Users\gerar>ssh bandit18@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
  For more information regarding individual wargames, visit
  ...
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

Byebye !
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
bandit18@bandit.labs.overthewire.org's password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

C:\Users\gerar> ssh bandit19@bandit.labs.overthewire.org -p 2220
Enter password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
### Notas Adicionales
Para este nivel tuvimos que hacer un inicio en la terminal de manera forzada, ya que al momento de iniciar el bash había sido personalizado para que nos sacara cada que iniciemos el bash. Por ello, en la forma que elegí lo que hicimos fue iniciar el bash desde su ruta, luego poner la contraseña y después escribir "cat readme" para abrir el readme, al final, el bash nos devuelve el password después de haber agregado el password.
### Referencias
https://overthewire.org/wargames/bandit/bandit19.html