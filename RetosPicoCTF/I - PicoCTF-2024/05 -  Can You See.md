## Objetivo
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/131/unknown.zip).
## Solución
```
┌──(kali㉿kali)-[~/concursillo]
└─$ unzip unknown.zip 
                                                                             
┌──(kali㉿kali)-[~/concursillo]
└─$ exiftool ukn_reality.jpg 
ExifTool Version Number         : 12.67
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 20:05:57-04:00
File Access Date/Time           : 2024:03:13 23:10:56-04:00
File Inode Change Date/Time     : 2024:03:13 23:10:43-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4



Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==

picoCTF{ME74D47A_HIDD3N_d8c381fd}
```
## Notas adicionales
## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnROUlRjMFJEUTNRVjlJU1VSRU0wNWZaRGhqTXpneFptUjlDZz09