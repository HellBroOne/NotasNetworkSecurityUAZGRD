## Descripcion
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)

Las muñecas matrioskas son un conjunto de muñecas de madera de tamaño decreciente colocadas una dentro de otra. ¿Cuál es el último? Imagen: [esto](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)
### Pistas
1. Wait, you can hide files inside files? But how do you find them?

1. Espera, ¿puedes ocultar archivos dentro de archivos? Pero, ¿cómo los encuentras?
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg
--2024-03-24 01:13:08--  https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651634 (636K) [application/octet-stream]
Saving to: 'dolls.jpg'

dolls.jpg                                      100%[===================================================================================================>] 636.36K  --.-KB/s    in 0.005s  

2024-03-24 01:13:08 (118 MB/s) - 'dolls.jpg' saved [651634/651634]

hellbroone-picoctf@webshell:~$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

hellbroone-picoctf@webshell:~$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
hellbroone-picoctf@webshell:~$ cd base_images
hellbroone-picoctf@webshell:~/base_images$ open 2_c.jpg 
Error: no "view" rule for type "image/jpeg" passed its test case
       (for more information, add "--debug=1" on the command line)


Exiting via interrupt: 2


hellbroone-picoctf@webshell:~/base_images$ unzip 2_c.jpg
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
hellbroone-picoctf@webshell:~/base_images$ cd base_images
hellbroone-picoctf@webshell:~/base_images/base_images$ open 3_c.jpg
Error: no "view" rule for type "image/jpeg" passed its test case
       (for more information, add "--debug=1" on the command line)

Can't Access `file://localhost/home/hellbroone-picoctf/base_images/base_images/3_c.jpg'
Alert!: Unable to access document.

lynx: Can't access startfile 
/usr/bin/open: 882: links2: not found
/usr/bin/open: 882: elinks: not found
/usr/bin/open: 882: links: not found

Can't Access `file://localhost/home/hellbroone-picoctf/base_images/base_images/3_c.jpg'
Alert!: Unable to access document.

lynx: Can't access startfile 
/usr/bin/open: 882: w3m: not found
xdg-open: no method available for opening '3_c.jpg'
hellbroone-picoctf@webshell:~/base_images/base_images$ cd base_images
-bash: cd: base_images: No such file or directory
hellbroone-picoctf@webshell:~/base_images/base_images$ unzip 3_c.jpg
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
hellbroone-picoctf@webshell:~/base_images/base_images$ cd base_images
hellbroone-picoctf@webshell:~/base_images/base_images/base_images$ open 4_c.jpg
Error: no "view" rule for type "image/jpeg" passed its test case
       (for more information, add "--debug=1" on the command line)

Can't Access `file://localhost/home/hellbroone-picoctf/base_images/base_images/base_images/4_c.jpg'
Alert!: Unable to access document.

lynx: Can't access startfile 
/usr/bin/open: 882: links2: not found
/usr/bin/open: 882: elinks: not found
/usr/bin/open: 882: links: not found
hellbroone-picoctf@webshell:~/base_images/base_images/base_images$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
hellbroone-picoctf@webshell:~/base_images/base_images/base_images$ cat flag.txt
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
hellbroone-picoctf@webshell:~/base_images/base_images/base_images$
```
### Notas Adicionales
Aprendimos que, generalmente una imagen tiene datos binarios, como los que se definen en la siguiente tabla.
```
Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
Video Card Gamma                : (Binary data 48 bytes, use -b option to extract)
Native Display Info             : (Binary data 62 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04861 0.02332 -0.05034 0.03018 0.99002 -0.01714 -0.00922 0.01503 0.75172
Make And Model                  : (Binary data 40 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
```
 Y también conocimos, _Binwalk_ es una herramienta destinada a la extracción de datos de imágenes binarias de firmware (proceso más conocido como «Firmware hacking»).
### Referencias
https://play.picoctf.org/practice/challenge/129