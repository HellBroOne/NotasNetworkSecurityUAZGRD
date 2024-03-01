## Descripcion
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) has extraordinarily helpful information...

¿Puedes invocar indicadores de ayuda para una herramienta o binario? [Este programa](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) tiene información extraordinariamente útil...
### Pistas
1. This program will only work in the webshell or another Linux computer.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm`
3. Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
4. -h and --help are the most common arguments to give to programs to get more information from them!
5. Not every program implements help features like -h and --help.
### Solución
```
hellbroone-picoctf@webshell:~$ ls
README.txt  flag  warm
hellbroone-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
hellbroone-picoctf@webshell:~$  wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
--2024-03-01 04:29:28--  https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm.1'

warm.1                                         100%[===================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-03-01 04:29:28 (352 MB/s) - 'warm.1' saved [10936/10936]

hellbroone-picoctf@webshell:~$ chmod +x warm
hellbroone-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
hellbroone-picoctf@webshell:~$ warm -h
-bash: warm: command not found
hellbroone-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
hellbroone-picoctf@webshell:~$ exit
logout
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/170