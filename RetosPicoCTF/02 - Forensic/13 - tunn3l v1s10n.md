## Descripción
We found this [file](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recover the flag.

Encontramos este [archivo](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recuperar la bandera.
### Pistas
1. Weird that it won't display right...

1. Es extraño que no se muestre correctamente...
### Solución
```
┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ file tunn3l_v1s10n
tunn3l_v1s10n: data

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ xxd -l 100 tunn3l_v1s10n
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333                                0'#3

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ hexeditor tunn3l_v1s10n

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ file tunn3l_v1s10n      
tunn3l_v1s10n: PC bitmap, Windows 3.x format, 1134 x 306 x 24, image size 2893400, resolution 5669 x 5669 px/m, cbSize 2893454, bits offset 40

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ open tunn3l_v1s10n

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ hexeditor tunn3l_v1s10n

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ exiftool tunn3l_v1s10n
ExifTool Version Number         : 12.67
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2024:03:21 14:46:22-04:00
File Access Date/Time           : 2024:03:21 14:46:26-04:00
File Inode Change Date/Time     : 2024:03:21 14:46:22-04:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 1134
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x1134
Megapixels                      : 1.3

┌──(kali㉿kali)-[~/picoctf/forensic/parte3/tunnelvision]
└─$ open tunn3l_v1s10n    
[BANDERA]: picoCTF{qu1t3_a_v13w_2020}
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