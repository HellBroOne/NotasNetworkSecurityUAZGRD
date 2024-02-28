# Level 26
## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!

¡Buen trabajo consiguiendo un shell! ¡Ahora date prisa y consigue la contraseña de bandit27!
### Datos de Acceso al nivel
Comandos: ls
Usuario: bandit26
Contraseña:  *c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1* (Nivel 26), *YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS* (Nivel 27)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 26 y estando en el vim)
**EN CORTO**
```
[Desde vim]
:sh
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ ./bandit27-do
Run a command as another user.
  Example: ./bandit27-do id
bandit26@bandit:~$ ./bandit27-do whoami
bandit27
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$ exit
[Salimos a VIM]

C:\Users\gerar>ssh bandit27@bandit.labs.overthewire.org -p 2220
Enter password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
### Notas Adicionales
En este nivel fue la continuación del nivel 26, ya que una vez en la consola del nivel 26, tuvimos que apresurarnos a obtener la contraseña del siguiente nivel, haciendo uso de ls y ejecutando el archivo de "bandit27-do" y haciendo uso de un comando como otro usuario.
### Referencias
https://overthewire.org/wargames/bandit/bandit27.html