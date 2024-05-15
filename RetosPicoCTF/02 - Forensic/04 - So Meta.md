## Descripción
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).

Encuentra la bandera en esta [imagen](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).
### Pistas
1. What does meta mean in the context of files?
2. Ever heard of metadata?

1. ¿Qué significa meta en el contexto de los archivos?
2. ¿Has oído hablar alguna vez de los metadatos?
### Solución
```
hellbroone-picoctf@webshell:~/forensic/someta$ wget https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png
--2024-03-12 18:25:25--  https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: 'pico_img.png'

pico_img.png                                   100%[===================================================================================================>] 106.25K  --.-KB/s    in 0.001s  

2024-03-12 18:25:25 (137 MB/s) - 'pico_img.png' saved [108795/108795]

hellbroone-picoctf@webshell:~/forensic/someta$ sudo apt install exiftool
-bash: sudo: command not found
hellbroone-picoctf@webshell:~/forensic/someta$ strings -n 10 pico_img.png | grep pico
picoCTF{s0_m3ta_fec06741}
```
También se puede resolver buscando entre la metadata de un archivo.
### Notas Adicionales
En este reto visualizamos los metadatos de un archivo para poder encontrar la bandera, los metadatos son datos que podría decirse que "describen a los datos", en el caso de una imagen te pueden indicar el alto, ancho, canales de color, coordenadas de la imagen y varios otros aspectos sobre la imagen.
### Referencias
https://play.picoctf.org/practice/challenge/19