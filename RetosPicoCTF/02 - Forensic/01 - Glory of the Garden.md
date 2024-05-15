## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.

Este [jardín](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contiene más de lo que parece.
### Pistas
1. What is a hex editor?

1. ¿Qué es un editor hexadecimal?
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
--2024-03-12 18:17:05--  https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: 'garden.jpg'

garden.jpg                                     100%[===================================================================================================>]   2.19M  --.-KB/s    in 0.01s   

2024-03-12 18:17:05 (195 MB/s) - 'garden.jpg' saved [2295192/2295192]


hellbroone-picoctf@webshell:~$ dir
-j.ltdis.x86_64.txt  Addadshashanammu.zip  code.py       file       flag        level1.py  python  static.ltdis.strings.txt  strings    warm
Addadshashanammu     README.txt            codebook.txt  fixme2.py  garden.jpg  ltdis.sh   static  static.ltdis.x86_64.txt   strings.1  warm.1
hellbroone-picoctf@webshell:~$ mkdir forensic
hellbroone-picoctf@webshell:~$ cd forensic
hellbroone-picoctf@webshell:~/forensic$ mkdir gloryofgarden
hellbroone-picoctf@webshell:~/forensic$ cd..
-bash: cd..: command not found
hellbroone-picoctf@webshell:~/forensic$ cd ..
hellbroone-picoctf@webshell:~$ mv garden.jpg ./forensic/gloryofgarden
hellbroone-picoctf@webshell:~$ ls
-j.ltdis.x86_64.txt  Addadshashanammu.zip  code.py       file       flag      level1.py  python  static.ltdis.strings.txt  strings    warm
Addadshashanammu     README.txt            codebook.txt  fixme2.py  forensic  ltdis.sh   static  static.ltdis.x86_64.txt   strings.1  warm.1
hellbroone-picoctf@webshell:~$ cd ./forensic/gloryofgarden
hellbroone-picoctf@webshell:~/forensic/gloryofgarden$ ls
garden.jpg
hellbroone-picoctf@webshell:~/forensic/gloryofgarden$ strings -n 10 garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
```
### Notas Adicionales
Aquí usamos las decodificaciones de imágenes para poder obtener un mensaje cifrado, la idea fue usar un editor de hexadecimales preinstalado en linux.
### Referencias
https://play.picoctf.org/practice/challenge/44