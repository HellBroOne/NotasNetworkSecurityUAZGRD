## Descripcion
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

Encontramos este extraño mensaje transmitiéndose en los servidores, creemos que tenemos un esquema de descifrado que funciona. Descargue el mensaje [aquí](https://artifacts.picoctf.net/c/127/message.txt).Tome cada número mod 37 y asígnelo al siguiente conjunto de caracteres: 0-25 es el alfabeto (mayúsculas), 26-35 son los dígitos decimales y 36 es un guión bajo. Envuelva su mensaje descifrado en el formato de bandera picoCTF (es decir, `picoCTF{decrypted_message }`)
### Pistas
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

1. ¿Sabes qué significa `mod 37` ?
2. `mod 37` significa módulo 37. Da el resto de un número después de dividirlo por 37.
### Solución
```
[EN PYTHON HACEMOS EL SIGUIENTE CODIGO PARA OBTENER LAS BASES]
datos = open("message.txt").read().split()
flag = ""
s = ""
for n in datos:
	c = int(n)%37
	if c >= 0 and c <= 25:
		s = chr(c+65)
	elif c >= 26 and c <= 35:
		s = chr(c+22)
	else:
		s = "_"
	flag += s
print(flag)

[EN EL SHELL]
┌──(loro㉿KaliLinux)-[~]
└─$ ascii
Usage: ascii [-adxohv] [-t] [char-alias...]
   -t = one-line output  -a = vertical format
   -d = Decimal table  -o = octal table  -x = hex table  -b binary table
   -h = This help screen -v = version information
Prints all aliases of an ASCII character. Args may be chars, C \-escapes,
English names, ^-escapes, ASCII mnemonics, or numerics in decimal/octal/hex.

Dec Hex    Dec Hex    Dec Hex  Dec Hex  Dec Hex  Dec Hex   Dec Hex   Dec Hex  
  0 00 NUL  16 10 DLE  32 20    48 30 0  64 40 @  80 50 P   96 60 `  112 70 p
  1 01 SOH  17 11 DC1  33 21 !  49 31 1  65 41 A  81 51 Q   97 61 a  113 71 q
  2 02 STX  18 12 DC2  34 22 "  50 32 2  66 42 B  82 52 R   98 62 b  114 72 r
  3 03 ETX  19 13 DC3  35 23 #  51 33 3  67 43 C  83 53 S   99 63 c  115 73 s
  4 04 EOT  20 14 DC4  36 24 $  52 34 4  68 44 D  84 54 T  100 64 d  116 74 t
  5 05 ENQ  21 15 NAK  37 25 %  53 35 5  69 45 E  85 55 U  101 65 e  117 75 u
  6 06 ACK  22 16 SYN  38 26 &  54 36 6  70 46 F  86 56 V  102 66 f  118 76 v
  7 07 BEL  23 17 ETB  39 27 '  55 37 7  71 47 G  87 57 W  103 67 g  119 77 w
  8 08 BS   24 18 CAN  40 28 (  56 38 8  72 48 H  88 58 X  104 68 h  120 78 x
  9 09 HT   25 19 EM   41 29 )  57 39 9  73 49 I  89 59 Y  105 69 i  121 79 y
 10 0A LF   26 1A SUB  42 2A *  58 3A :  74 4A J  90 5A Z  106 6A j  122 7A z
 11 0B VT   27 1B ESC  43 2B +  59 3B ;  75 4B K  91 5B [  107 6B k  123 7B {
 12 0C FF   28 1C FS   44 2C ,  60 3C <  76 4C L  92 5C \  108 6C l  124 7C |
 13 0D CR   29 1D GS   45 2D -  61 3D =  77 4D M  93 5D ]  109 6D m  125 7D }
 14 0E SO   30 1E RS   46 2E .  62 3E >  78 4E N  94 5E ^  110 6E n  126 7E ~
 15 0F SI   31 1F US   47 2F /  63 3F ?  79 4F O  95 5F _  111 6F o  127 7F DEL
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ python basmod1
python: can't open file '/home/loro/basmod1': [Errno 2] No such file or directory
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ python basmod1.py
python: can't open file '/home/loro/basmod1.py': [Errno 2] No such file or directory
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ cd basemod1    
cd: no such file or directory: basemod1
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ cd basicmod1
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/basicmod1]
└─$ python basmod1.py
Traceback (most recent call last):
  File "/home/loro/basicmod1/basmod1.py", line 1, in <module>
    datos = open("message.txt").read().split()
            ^^^^^^^^^^^^^^^^^^^
FileNotFoundError: [Errno 2] No such file or directory: 'message.txt'
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/basicmod1]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt
--2024-04-16 12:44:02--  https://artifacts.picoctf.net/c/127/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[=============================================>]      85  --.-KB/s    in 0s      

2024-04-16 12:44:03 (3.12 MB/s) - ‘message.txt’ saved [85/85]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/basicmod1]
└─$ python basmod1.py                                   
R0UND_N_R0UND_79C18FB3

```
### Notas Adicionales
El código ASCII (American Standard Code for Information Interchange) **es un sistema de codificación que asigna un valor numérico nico a diferentes caracteres utilizados en la comunicación electrónica**.
### Referencias
https://play.picoctf.org/practice/challenge/253
