## Descripcion
This file has a flag in plain sight (aka "in-the-clear").

Este archivo tiene una bandera a la vista (también conocida como "en-lo-claro").
### Pistas
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`
3. `$ man cat`
### Solución
```
hellbroone-picoctf@webshell:~$ ls
README.txt
hellbroone-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
--2024-02-27 18:35:43--  https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                           100%[===================================================================================================>]      34  --.-KB/s    in 0s      

2024-02-27 18:35:43 (14.3 MB/s) - 'flag' saved [34/34]

hellbroone-picoctf@webshell:~$ ls
README.txt  flag
hellbroone-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
hellbroone-picoctf@webshell:~$ 
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/147