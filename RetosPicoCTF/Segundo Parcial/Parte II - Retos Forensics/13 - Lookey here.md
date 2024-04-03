## Descripcion
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).

Los atacantes han ocultado información de datos en gran masa en el pasado, tal vez todavía lo estén haciendo. Descarga los datos [aquí](https://artifacts.picoctf.net/c/124/anthem.flag.txt).
### Pistas
1. Download the file and search for the flag based on the known prefix.

1. Descarga el archivo y busca la bandera según el prefijo conocido.
### Solución
```
┌──(loro㉿KaliLinux)-[~]
└─$ wget https://artifacts.picoctf.net/c/124/anthem.flag.txt 
--2024-04-02 17:40:44--  https://artifacts.picoctf.net/c/124/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt          100%[==================================>] 106.12K  29.4KB/s    in 3.6s    

2024-04-02 17:40:52 (29.4 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]
                                                                                                    
┌──(loro㉿KaliLinux)-[~]
└─$ head anthem.flag.txt
      ANTHEM

      by Ayn Rand


        CONTENTS

         PART ONE

         PART TWO
                                                                                                    
┌──(loro㉿KaliLinux)-[~]
└─$ file anthem.flag.txt
anthem.flag.txt: Unicode text, UTF-8 text
                                                                                                    
┌──(loro㉿KaliLinux)-[~]
└─$ strings anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
```
### Notas Adicionales
**grep** es una utilidad de la línea de comandos escrita originalmente para ser usada con el sistema operativo Unix. Usualmente, grep toma una expresión regular de la línea de comandos, lee la entrada estándar o una lista de archivos, e imprime las líneas que contengan coincidencias.
### Referencias
https://play.picoctf.org/practice/challenge/279