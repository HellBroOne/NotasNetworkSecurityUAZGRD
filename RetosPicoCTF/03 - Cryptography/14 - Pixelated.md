## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

Tengo estas 2 imágenes, ¿puedes hacer una bandera con ellas? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1 .png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scra mbled2.png)
### Pistas
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images

1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Piensa en diferentes formas de "apilar" imágenes.
### Solución
```
┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
--2024-04-16 13:11:01--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197176 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png               100%[=============================================>] 192.55K   282KB/s    in 0.7s    

2024-04-16 13:11:02 (282 KB/s) - ‘scrambled1.png’ saved [197176/197176]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
--2024-04-16 13:11:06--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png               100%[=============================================>] 192.55K   277KB/s    in 0.7s    

2024-04-16 13:11:07 (277 KB/s) - ‘scrambled2.png’ saved [197174/197174]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ open scrambled1.png
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ sudo apt install imagemagick
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
imagemagick is already the newest version (8:6.9.12.98+dfsg1-5+b1).
imagemagick set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 493 not upgraded.

┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png 
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/pixelated]
└─$ open flag.png 

picoCTF{d562333d}
```
![[Pasted image 20240416131727.png]]
### Notas Adicionales
La criptografía visual es una técnica criptográfica que permite cifrar información visual (imágenes, texto, etc.) de tal manera que la información descifrada aparezca como una imagen visual.
### Referencias
https://play.picoctf.org/practice/challenge/100
