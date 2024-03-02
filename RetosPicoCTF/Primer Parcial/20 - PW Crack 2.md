## Descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/14/level2.py) y necesitarás la [bandera](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) cifrada también en el mismo directorio.
### Pistas
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/14/level2.py
--2024-03-02 03:40:09--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                      100%[===================================================================================================>]     914  --.-KB/s    in 0s      

2024-03-02 03:40:09 (41.6 MB/s) - 'level2.py' saved [914/914]

hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2024-03-02 03:40:19--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                            100%[===================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-02 03:40:19 (585 KB/s) - 'level2.flag.txt.enc' saved [31/31]

hellbroone-picoctf@webshell:~/python$ chmod +x level2.py 
hellbroone-picoctf@webshell:~/python$ python level2.py
Please enter correct password for flag: nose
That password is incorrect
hellbroone-picoctf@webshell:~/python$ nano level2.py
```
[EN PYTHON:]
```
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

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
```
[SALIMOS DE PYTHON]
```
hellbroone-picoctf@webshell:~/python$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
>>> exit()
hellbroone-picoctf@webshell:~/python$ python level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
hellbroone-picoctf@webshell:~/python$ exit
```
### Notas Adicionales
Para este nivel usamos nano, para poder verificar una contraseña que ya venía dentro del código y poder usarla para acceder al sistema, sin embargo esta vez la contraseña venía cifrada en el código de python, para ello se utilizaron los métodos de chr() de python para descifrarla. Una vez ingresada la contraseña correcta se nos dará la bandera.
### Referencias
https://play.picoctf.org/practice/challenge/246