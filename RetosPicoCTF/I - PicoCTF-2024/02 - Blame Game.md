## Objetivo
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

Las confirmaciones de alguien parecen estar impidiendo que el programa funcione. ¿Quién es?Puedes descargar los archivos del reto aquí:
## Pistas

## Solución
```
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame]
└─$ wget 'https://artifacts.picoctf.net/c_titan/159/challenge.zip'
--2024-03-13 23:01:27--  https://artifacts.picoctf.net/c_titan/159/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.3, 3.161.225.60, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293915 (287K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip       100%[================>] 287.03K  --.-KB/s    in 0.1s    

2024-03-13 23:01:28 (2.46 MB/s) - ‘challenge.zip’ saved [293915/293915]

                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame]
└─$ ls
challenge.zip
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
 extracting: drop-in/message.py      
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
  ... 
  ... 
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame]
└─$ ls
challenge.zip  drop-in
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame]
└─$ cd drop-in  
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame/drop-in]
└─$ ls
message.py
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame/drop-in]
└─$ git blame message.py 
23e9d4ce (picoCTF{@sk_th3_1nt3rn_81e716ff} 2024-03-12 00:07:15 +0000 1) print("Hello, World!"
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/blameGame/drop-in]
└─$ 



```
## Notas Adicionales
**Git Blame**: El comando git blame puedes ver quién, ha hecho cambios en un archivo específico, línea por línea, lo cual es útil si trabajas en equipo, en lugar de hacerlo solo.

## Referencias
https://www.freecodecamp.org/espanol/news/explicacion-de-git-blame-con-ejemplos/
