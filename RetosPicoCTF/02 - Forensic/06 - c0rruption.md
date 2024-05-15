## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Encontramos este [archivo](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recupera la bandera.
### Pistas
1. Try fixing the file header

1. Intenta arreglar el encabezado del archivo.
### Solución
```
1. Necesitamos tener en cuenta que el archivo que se tiene es un archivo PNG, por ello, hay que verificar como manejar los chunks de una imagen png.
2. Para poder comprender la estructura de un png, es recomendable ver la estructura aquí: https://en.wikipedia.org/wiki/PNG
3. Reparamos el header con hexeditor en linux para editar los datos hexadecimales de este archivo.
4. Reemplazamos los hexadecimales que necesiten ser reparados.
5. Obtenemos la bandera: picoCTF{c0rrupt10n_1847995}

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ wget 'https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery'

--2024-03-19 14:42:55--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’
mystery               100%[=======================>] 198.18K  --.-KB/s    in 0.1s    
2024-03-19 14:42:56 (1.66 MB/s) - ‘mystery’ saved [202940/202940]

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ file mystery      
mystery: data

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ ls
mystery

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ xxd -l 100 mystery            
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71  

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ pngcheck -v mystery
File: mystery (202940 bytes)
invalid chunk name "C"DR" (43 22 44 52)
ERRORS DETECTED in mystery
(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ hexeditor mystery  

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ hexeditor mystery  

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  invalid chunk name "�DET" (ffffffab 44 45 54)
ERRORS DETECTED in mystery
(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ hexeditor mystery  

(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
(kali㉿kali)-[~/picoctf/forensic/parte2/c0rrupt]$ fim mystery        

picoCTF{c0rrupt10n_1847995}
```
### Notas Adicionales
Para poder hacer este reto, fue necesario comprender sobre la estructura de una imagen PNG, sobre la estructura de archivo de esta imagen. Un archivo PNG comienza con una firma de 8 bytes. Después del encabezado, viene una serie de fragmentos, cada uno de los cuales transmite cierta información sobre la imagen.
### Referencias
https://play.picoctf.org/practice/challenge/53
***PNG Wikipedia:*** https://en.wikipedia.org/wiki/PNG