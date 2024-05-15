## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?

¿Puedes encontrar la bandera en [archivo](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) sin ejecutarlo?
### Pistas
1. [strings](https://linux.die.net/man/1/strings)
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings

hellbroone-picoctf@webshell:~$ ls
-j.ltdis.x86_64.txt  Addadshashanammu.zip  code.py       file  ltdis.sh  static                    static.ltdis.x86_64.txt  strings.1  warm.1
Addadshashanammu     README.txt            codebook.txt  flag  python    static.ltdis.strings.txt  strings                  warm
hellbroone-picoctf@webshell:~$ strings strings | grep 'picoCTF{'
picoCTF{5tRIng5_1T_827aee91}
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel hicimos uso del método **strings** que permite obtener todas las cadenas legibles en un archivo que no es txt, pero dichas cadenas sean legibles en ASCII. La idea es que con strings y ayudandonos de grep se pueda obtener una salida que se parezca a la bandera que necesitamos.
### Referencias
https://play.picoctf.org/practice/challenge/37