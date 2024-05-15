## Objetivo
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/16/challenge.zip)
## Solución
```
──(kali㉿kali)-[~/concursillo/Fore]
└─$ wget https://artifacts.picoctf.net/c_atlas/16/challenge.zip
--2024-03-13 23:40:45--  https://artifacts.picoctf.net/c_atlas/16/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 736 [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip       100%[================>]     736  --.-KB/s    in 0s      

2024-03-13 23:40:46 (38.2 MB/s) - ‘challenge.zip’ saved [736/736]

                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
 extracting: home/ctf-player/drop-in/flag.png  
                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore]
└─$ ls                     
challenge.zip  home
                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore]
└─$ cd home 
                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore/home]
└─$ cd ctf-player 
                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore/home/ctf-player]
└─$ ls                     
drop-in
                                                                             
┌──(kali㉿kali)-[~/concursillo/Fore/home/ctf-player]
└─$ cd drop-in   
                                                                             
┌──(kali㉿kali)-[~/…/Fore/home/ctf-player/drop-in]
└─$ open flag.png 

Escaneamos el codigo QR y nos arroja:
picoCTF{p33k_@_b00_7843f77c}
```
## Notas adicionales
## Referencias