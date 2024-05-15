## Descripción
Fix the syntax error in this Python script to print the flag.

Corrije el error de sintaxis en este script de Python para imprimir la bandera.
### Pistas
1. Indentation is very meaningful in Python.
2. To view the file in the webshell, do: `$ nano fixme1.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~$ cd python
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/25/fixme1.py
--2024-03-02 00:24:16--  https://artifacts.picoctf.net/c/25/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                      100%[===================================================================================================>]     837  --.-KB/s    in 0s      

2024-03-02 00:24:16 (299 MB/s) - 'fixme1.py' saved [837/837]

hellbroone-picoctf@webshell:~/python$ ls -la
total 20
drwxrwxr-x 2 hellbroone-picoctf hellbroone-picoctf   78 Mar  2 00:24 .
drwxr-xr-x 5 hellbroone-picoctf hellbroone-picoctf 4096 Mar  2 00:13 ..
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1278 Mar 16  2023 code.py
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf   27 Mar 16  2023 codebook.txt
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1189 Mar 16  2023 convertme.py
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf  837 Mar 16  2023 fixme1.py
hellbroone-picoctf@webshell:~/python$ chmod +x fixme1.py
hellbroone-picoctf@webshell:~/python$ python fixme1.py
  File "/home/hellbroone-picoctf/python/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
hellbroone-picoctf@webshell:~/python$ nano fixme1.py
hellbroone-picoctf@webshell:~/python$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
hellbroone-picoctf@webshell:~/python$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel hicimos uso de ***nano** que es un editor de texto incluido en Linux*, la idea es la de verificar que el código esté funcionando, pero la idea en este caso es que en python la identación se les fue de las manos, haciendo uso de identación no necesaria para una línea, esto simplemente con nano para borrar dos espacios salidos.
### Referencias
https://play.picoctf.org/practice/challenge/240