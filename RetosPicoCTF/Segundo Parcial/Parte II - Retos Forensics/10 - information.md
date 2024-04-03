## Descripcion
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)

Los archivos siempre se pueden cambiar de forma secreta. ¿Puedes encontrar la bandera? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)
### Pistas
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

1. Mira los detalles del archivo.
2. Asegúrese de enviar la bandera como picoCTF{XXXXX}
### Solución
```
┌──(loro㉿KaliLinux)-[~]
└─$ wget https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg
--2024-04-01 16:27:58--  https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg             100%[================>] 857.55K  39.8KB/s    in 14s     

2024-04-01 16:28:19 (60.8 KB/s) - ‘cat.jpg’ saved [878136/878136]

                                                                             
┌──(loro㉿KaliLinux)-[~]
└─$ file cat.jpg       
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
                                                                             
┌──(loro㉿KaliLinux)-[~]
└─$ stat cat.jpg
  File: cat.jpg
  Size: 878136          Blocks: 1720       IO Block: 4096   regular file
Device: 8,1     Inode: 948731      Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/    loro)   Gid: ( 1000/    loro)
Access: 2024-04-01 16:28:26.988474914 -0600
Modify: 2021-03-15 12:24:46.000000000 -0600
Change: 2024-04-01 16:28:19.336650865 -0600
 Birth: 2024-04-01 16:28:05.217594774 -0600
                                                                                                              
┌──(loro㉿KaliLinux)-[~]
└─$ exiftool cat.jpg
ExifTool Version Number         : 12.76
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2024:04:01 16:28:26-06:00
File Inode Change Date/Time     : 2024:04:01 16:28:19-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1

┌──(loro㉿KaliLinux)-[~]
└─$ echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d

picoCTF{the_m3tadata_1s_modified} 
```
### Notas Adicionales
El comando *exiftool* funciona para obtener la metadata de un archivo y poder saber que hay dentro de ese archivo como lo es el autor, coordenadas, dimensiones y otras cosas de un archivo.
La opción -d de base64 nos permite decodificar de una base64.
### Referencias
https://play.picoctf.org/practice/challenge/186