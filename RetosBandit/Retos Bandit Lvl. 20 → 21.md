# Level 20
## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
**NOTE:** Try connecting to your own network daemon to see if it works as you think

Hay un binario setuid en el directorio de inicio que hace lo siguiente: establece una conexión con el host local en el puerto que especifica como argumento de la línea de comando. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (bandit20). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (bandit21).
**NOTA:** Intente conectarse a su propio demonio de red para ver si funciona como cree
### Datos de Acceso al nivel
Comandos: ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)
Usuario: bandit20
Contraseña:  *VxCazJaVykI6W36BkBU0mJTCM8rR95XT* (Nivel 20), *NvEJF7oVjkddltPSrdKEFOllh9V1IBcq* (Nivel 21)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 20)
```
bandit20@bandit:~$ nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 4147521
bandit20@bandit:~$ Listening on 0.0.0.0 2020

bandit20@bandit:~$ ./suconnect 2020
Connection received on 127.0.0.1 53142
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:\Users\gerar>ssh bandit21@bandit.labs.overthewire.org -p 2220
Enter password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```
### Notas Adicionales
Para este nivel se volvió a hacer uso de un binario setuid, y luego se le paso el password del nivel actual, este password es comparado por el binario y si son los mismos entonces nos manda el siguiente password.
### Referencias
https://overthewire.org/wargames/bandit/bandit21.html