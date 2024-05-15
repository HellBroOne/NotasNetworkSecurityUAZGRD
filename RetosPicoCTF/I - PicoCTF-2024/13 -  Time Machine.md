## Objetivo
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

¿En qué estuve trabajando por última vez? Recuerdo que escribí una nota para ayudarme a recordar...Puedes descargar los archivos del reto aquí:
## Pistas

## Solución
```
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine]
└─$ wget 'https://artifacts.picoctf.net/c_titan/163/challenge.zip' 
--2024-03-13 22:36:28--  https://artifacts.picoctf.net/c_titan/163/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.32, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17741 (17K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip       100%[================>]  17.33K  --.-KB/s    in 0s      

2024-03-13 22:36:28 (178 MB/s) - ‘challenge.zip’ saved [17741/17741]

                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine]
└─$ ls
challenge.zip
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine]
└─$ unzip challenge.zip               
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
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
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/e6/
 extracting: drop-in/.git/objects/e6/5fedb3a72a16c577f4b17023b63997134b307d  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine]
└─$ ls
challenge.zip  drop-in
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine]
└─$ cd drop-in    
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine/drop-in]
└─$ ls
message.txt
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine/drop-in]
└─$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine/drop-in]
└─$ git log                                              
commit e65fedb3a72a16c577f4b17023b63997134b307d (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:29 2024 +0000

    picoCTF{t1m3m@ch1n3_88c35e3b}
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/timeMachine/drop-in]
└─$ 

```
## Notas Adicionales

## Referencias
