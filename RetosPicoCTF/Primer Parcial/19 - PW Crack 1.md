## Descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas [aquí](https://artifacts.picoctf.net/c/12/level1.py) y necesitarás la [bandera] cifrada(https:/ /artifacts.picoctf.net/c/12/level1.flag.txt.enc) también en el mismo directorio.
### Pistas
1. To view the file in the webshell, do: `$ nano level1.py`
2. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
3. The `str_xor` function does not need to be reverse engineered for this challenge.
### Solución
```
hellbroone-picoctf@webshell:~$ cd python
hellbroone-picoctf@webshell:~/python$ https://artifacts.picoctf.net/c/12/level1.py
-bash: https://artifacts.picoctf.net/c/12/level1.py: No such file or directory
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/12/level1.py
--2024-03-02 03:29:45--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                      100%[===================================================================================================>]     876  --.-KB/s    in 0s      

2024-03-02 03:29:45 (36.1 MB/s) - 'level1.py' saved [876/876]

hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2024-03-02 03:30:00--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                            100%[===================================================================================================>]      30  --.-KB/s    in 0s      

2024-03-02 03:30:00 (8.97 MB/s) - 'level1.flag.txt.enc' saved [30/30]
hellbroone-picoctf@webshell:~/python$ ls -la
total 28
drwxrwxr-x 2 hellbroone-picoctf hellbroone-picoctf  122 Mar  2 03:30 .
drwxr-xr-x 6 hellbroone-picoctf hellbroone-picoctf 4096 Mar  2 03:29 ..
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1278 Mar 16  2023 code.py
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf   27 Mar 16  2023 codebook.txt
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1189 Mar 16  2023 convertme.py
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf  833 Mar  2 00:25 fixme1.py
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf   30 Mar 16  2023 level1.flag.txt.enc
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf  876 Mar 16  2023 level1.py
hellbroone-picoctf@webshell:~/python$ chmod +x level1.py
hellbroone-picoctf@webshell:~/python$ python level1.py
Please enter correct password for flag: jd
That password is incorrect
hellbroone-picoctf@webshell:~/python$ nano level1.py
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"): <<< USAMOS ESTE PASSWORD
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
```
[SALIMOS DE PYTHON]
```
hellbroone-picoctf@webshell:~/python$ python level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
hellbroone-picoctf@webshell:~/python$ exit
```
### Notas Adicionales
Para este nivel usamos nano, para poder verificar una contraseña que ya venía dentro del código y poder usarla para acceder al sistema. Una vez ingresada la contraseña correcta se nos dará la bandera.
### Referencias
https://play.picoctf.org/practice/challenge/245