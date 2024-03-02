## Descripcion
Run the Python script `code.py` in the same directory as `codebook.txt`.

Ejecute el script Python `code.py` en el mismo directorio que `codebook.txt`.
### Pistas
1. On the webshell, use `ls` to see if both files are in the directory you are in.
2. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~$ mkdir python
hellbroone-picoctf@webshell:~$ cd python
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/2/codebook.txt
--2024-03-01 22:38:43--  https://artifacts.picoctf.net/c/2/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                   100%[===================================================================================================>]      27  --.-KB/s    in 0s      

2024-03-01 22:38:43 (457 KB/s) - 'codebook.txt' saved [27/27]

hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/2/code.py
--2024-03-01 22:39:00--  https://artifacts.picoctf.net/c/2/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                        100%[===================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-03-01 22:39:00 (62.1 MB/s) - 'code.py' saved [1278/1278]

hellbroone-picoctf@webshell:~/python$ ls -la
total 12
drwxrwxr-x 2 hellbroone-picoctf hellbroone-picoctf   41 Mar  1 22:39 .
drwxr-xr-x 5 hellbroone-picoctf hellbroone-picoctf 4096 Mar  1 22:38 ..
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf 1278 Mar 16  2023 code.py
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf   27 Mar 16  2023 codebook.txt
hellbroone-picoctf@webshell:~/python$ chmod +x code.py
hellbroone-picoctf@webshell:~/python$ chmod +x codebook.txt
hellbroone-picoctf@webshell:~/python$ ls -la
total 12
drwxrwxr-x 2 hellbroone-picoctf hellbroone-picoctf   41 Mar  1 22:39 .
drwxr-xr-x 5 hellbroone-picoctf hellbroone-picoctf 4096 Mar  1 22:38 ..
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1278 Mar 16  2023 code.py
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf   27 Mar 16  2023 codebook.txt
hellbroone-picoctf@webshell:~/python$ ./code.py
import-im6.q16: unable to open X server `' @ error/import.c/ImportImageCommand/346.
import-im6.q16: unable to open X server `' @ error/import.c/ImportImageCommand/346.
./code.py: line 7: syntax error near unexpected token `('
./code.py: line 7: `def str_xor(secret, key):'
hellbroone-picoctf@webshell:~/python$ python code.py
picoCTF{c0d3b00k_455157_7d102d7a}
hellbroone-picoctf@webshell:~/python$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Aquí aprendimos a abrir un script desde python, pero en este caso, ejecutándolo con el comando de *python* para iniciar un script de python.
### Referencias
https://play.picoctf.org/practice/challenge/238