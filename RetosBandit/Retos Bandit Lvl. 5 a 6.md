# Level 5
## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

La contraseña para el siguiente nivel se almacena en un archivo en algún lugar del directorio interno y tiene todas las siguientes propiedades:
- legible por humanos
- 1033 bytes de tamaño
- no ejecutable
### Datos de Acceso al nivel
Comandos: ls , cd , cat , file , du , find
Usuario: bandit5
Contraseña: *P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU* (Descubierta)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 5)
```

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd ./inhere
bandit5@bandit:~/inhere$ dir
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit5@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit6@bandit.labs.overthewire.org -p 2220
Enter password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
### Notas Adicionales
Este nivel demostró un poco más de complejidad de búsqueda, ya que se nos pedían más características de lo que se tenía que hacer, pero pudimos resolverla con varias opciones y comandos como lo son:
**find**: find se utiliza para encontrar archivos en un determinado directorio a partir de diversas reglas de búsqueda.
*-type*: opción de find que permite buscar solamente archivos que contengan una letra o cadena especifica.
*-size*: opción de find que busca un archivo con un tamaño específico
### Referencias
https://overthewire.org/wargames/bandit/bandit6.html