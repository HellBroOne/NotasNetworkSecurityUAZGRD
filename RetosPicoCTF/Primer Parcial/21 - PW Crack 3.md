## Descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/18/level3.py) y necesitarás la [bandera](https:/ /artifacts.picoctf.net/c/18/level3.flag.txt.enc) y el [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) también en el mismo directorio. Hay 7 contraseñas potenciales y 1 es correcta. Puedes encontrarlos examinando el script de verificación de contraseñas.
### Pistas
1. To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2. To exit `bvi` type `:q` and press enter.
3. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/18/level3.py
--2024-03-02 03:52:35--  https://artifacts.picoctf.net/c/18/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                      100%[===================================================================================================>]   1.31K  --.-KB/s    in 0s      

2024-03-02 03:52:35 (75.7 MB/s) - 'level3.py' saved [1337/1337]

hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
--2024-03-02 03:52:44--  https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                            100%[===================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-02 03:52:44 (1.45 MB/s) - 'level3.flag.txt.enc' saved [31/31]

hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/18/level3.hash.bin
--2024-03-02 03:52:54--  https://artifacts.picoctf.net/c/18/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                100%[===================================================================================================>]      16  --.-KB/s    in 0s      

2024-03-02 03:52:54 (734 KB/s) - 'level3.hash.bin' saved [16/16]

hellbroone-picoctf@webshell:~/python$ ls
code.py  codebook.txt  convertme.py  fixme1.py  level1.flag.txt.enc  level1.py  level2.flag.txt.enc  level2.py  level3.flag.txt.enc  level3.hash.bin  level3.py
hellbroone-picoctf@webshell:~/python$ chmod +x level3.py
hellbroone-picoctf@webshell:~/python$ python level3.py
Please enter correct password for flag: sabe
That password is incorrect
hellbroone-picoctf@webshell:~/python$ nano level3.py
```
[EN PYTHON:]
```
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
```
[SALIMOS DE PYTHON]

[EN BVI]
```
00000000  16 02 6D 60 FF 9B 54 41 0B 34 35 B4 03 AF D2 26                                                                                     ..m`..TA.45....&
~
~
~
~
~
~
~
~
~
~
~
~
~
~
"level3.hash.bin" 16 bytes 
```
[SALIMOS DE BVI]
```
hellbroone-picoctf@webshell:~/python$ python level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
hellbroone-picoctf@webshell:~/python$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel usamos nano, para ver un script de python que contiene una función de hash que codifica las contraseñas, la idea es que verificamos estas contraseñas y pudimos descifrar una que sea la necesaria.

### Referencias
https://play.picoctf.org/practice/challenge/247