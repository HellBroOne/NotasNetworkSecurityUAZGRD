## Descripcion
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `64287` to get the flag?

Usar netcat (nc) será bastante importante. ¿Puedes conectarte a `jupiter.challenges.picoctf.org` en el puerto `64287` para obtener la bandera?
### Pistas
1. nc [tutorial](https://linux.die.net/man/1/nc)
### Solución
```
hellbroone-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 64287 
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_284be8f7}
^C
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel hicimos uso de netcat, este nos ha servido desde los retos Bandit para poder oir conexiones en varios puertos desde servidores remotos, para esto simplemente hay que escribir **nc** seguido del servidor al que nos vayamos a conectar y en qué puerto
### Referencias
https://play.picoctf.org/practice/challenge/34