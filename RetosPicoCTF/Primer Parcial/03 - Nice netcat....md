## Descripcion
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...
### Pistas
1. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2. You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

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