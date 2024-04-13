## Descripcion
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.

Descifremos esto: [texto cifrado](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Algo parece un poco pequeño.
### Pistas
1. RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
2. How could having too small an e affect the security of this 2048 bit key?
3. Make sure you don't lose precision, the numbers are pretty big (besides the e value)

1. RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
2. ¿Cómo podría afectar una e demasiado pequeña a la seguridad de esta clave de 2048 bits?
3. Asegúrate de no perder precisión, los números son bastante grandes (aparte del valor e)
### Solución
```
┌──(loro㉿KaliLinux)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
--2024-04-12 21:22:11--  https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 884 [application/octet-stream]
Saving to: ‘ciphertext.1’

ciphertext.1                 100%[=============================================>]     884  --.-KB/s    in 0s      

2024-04-12 21:22:12 (7.79 MB/s) - ‘ciphertext.1’ saved [884/884]
┌──(loro㉿KaliLinux)-[~]
└─$ cat ciphertext.1

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933 
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ mousepad exploitation1.py
^C                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ echo "si c = m ^ e mod n, entonces m = sqrt(c, e)"
si c = m ^ e mod n, entonces m = sqrt(c, e)
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ echo "c = m ^ 3"                               
c = m ^ 3
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ echo " m = sqrt(c, 3)"                            
 m = sqrt(c, 3)

┌──(loro㉿KaliLinux)-[~]
└─$ sudo python3 -m pip install gmpy2 
[sudo] password for loro: 
Collecting gmpy2
  Downloading gmpy2-2.1.5-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.0 kB)
Downloading gmpy2-2.1.5-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (1.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 285.1 kB/s eta 0:00:00
Installing collected packages: gmpy2
Successfully installed gmpy2-2.1.5
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv         
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ sudo python3 -m pip install pycryptodome
Collecting pycryptodome
  Downloading pycryptodome-3.20.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (3.4 kB)
Downloading pycryptodome-3.20.0-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.1 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 834.6 kB/s eta 0:00:00
Installing collected packages: pycryptodome
Successfully installed pycryptodome-3.20.0
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv         
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ python3
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import *
>>> from Crypto.Util.number import long_to_bytes
>>> gmpy2.get_context().precision = 2048
>>> c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933
>>> e = 3
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203708028670029596145277)
>>> print(long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_ccaa7776}'
>>> exit()

```
### Notas Adicionales
**El RSA (Rivest–Shamir–Adleman)** es un algoritmo utilizado por las computadoras modernas para cifrar y descifrar mensajes. Es un algoritmo criptográfico asimétrico. Asimétrico significa que hay dos claves diferentes.
Criptografía de Llave pública.
Nomenclatura:
***m =*** texto plano
***c =*** texto cifrado
***p =*** número primo
***q =*** número primo
***n =*** módulo
***e =*** llave pública (n^16+1 = )
***tn =*** totient (euler)
***d =*** llave privada

Fórmulas:
***n =*** p * q
***tn =*** (p - 1) * (q - 1)
***d =*** e mod inu tn -- pow(e, -1, tn)
***c =*** m ^ e mod n -- pow(m, e, n)
***m =*** c^d mod n -- pow(e, d, n)
### Referencias
https://play.picoctf.org/practice/challenge/73
**# RSA (cryptosystem):** https://en.wikipedia.org/wiki/RSA_(cryptosystem)