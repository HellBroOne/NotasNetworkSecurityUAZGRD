## Descripcion
Fix the syntax error in this Python script to print the flag.

Corrije el error de sintaxis en este script de Python para imprimir la bandera.
### Pistas
1. Are equality and assignment the same symbol?
2. To view the file in the webshell, do: `$ nano fixme1.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/6/fixme2.py
--2024-03-02 03:04:04--  https://artifacts.picoctf.net/c/6/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                      100%[===================================================================================================>]   1.00K  --.-KB/s    in 0s      

2024-03-02 03:04:04 (74.2 MB/s) - 'fixme2.py' saved [1029/1029]

hellbroone-picoctf@webshell:~$ chmod +x fixme2.py
hellbroone-picoctf@webshell:~$ python fixme2.py
  File "/home/hellbroone-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
hellbroone-picoctf@webshell:~$ nano fixme2.py
hellbroone-picoctf@webshell:~$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel hicimos uso de ***nano** que es un editor de texto incluido en Linux*, la idea es la de verificar que el código esté funcionando, pero la idea en este caso es que en python se les paso usar un "==" para hacer uso de una equidad, esto simplemente con nano para agregar un signo de igual (==).
### Referencias
https://play.picoctf.org/practice/challenge/241