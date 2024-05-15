## Descripción
I wonder what this really is... [enc](https://mercury.picoctf.net/static/1d8a5a2779c4dc24999f0358d7a1a786/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

Me pregunto qué es esto realmente... [enc](https://mercury.picoctf.net/static/1d8a5a2779c4dc24999f0358d7a1a786/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
### Pistas
1. You may find some decoders online

1. Puedes encontrar algunos decodificadores en línea
### Solución
```
┌──(loro㉿KaliLinux)-[~/transformation]
└─$ wget https://mercury.picoctf.net/static/1d8a5a2779c4dc24999f0358d7a1a786/enc
--2024-05-14 19:41:23--  https://mercury.picoctf.net/static/1d8a5a2779c4dc24999f0358d7a1a786/enc
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 57 [application/octet-stream]
Saving to: ‘enc’

enc                                                        100%[========================================================================================================================================>]      57  --.-KB/s    in 0s      

2024-05-14 19:41:24 (82.2 MB/s) - ‘enc’ saved [57/57]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/transformation]
└─$ file enc            
enc: Unicode text, UTF-8 text, with no line terminators
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/transformation]
└─$ cat enc            
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/transformation]
└─$ python                 
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> encoded = 灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽
  File "<stdin>", line 1
    encoded = 灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽
                        ^
SyntaxError: invalid character '㌴' (U+3334)
>>> encoded = '灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽'
>>> print(encoded.encode('utf-16-be'))
b'picoCTF{16_bits_inst34d_of_8_e703b486}'
>>> exit()

```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/104
