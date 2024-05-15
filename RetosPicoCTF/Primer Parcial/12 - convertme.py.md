## Descripción
Run the Python script and convert the given number from decimal to binary to get the flag.

Ejecute el script Python y convierta el número dado de decimal a binario para obtener la bandera.
### Pistas
1. Look up a decimal to binary number conversion app on the web or use your computer's calculator!
2. The `str_xor` function does not need to be reverse engineered for this challenge.
3. If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
4. To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
5. Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
6. Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`
### Solución
```
hellbroone-picoctf@webshell:~$ cd python
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2024-03-01 22:51:50--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                   100%[===================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-03-01 22:51:50 (530 MB/s) - 'convertme.py' saved [1189/1189]

hellbroone-picoctf@webshell:~/python$ ls -la
total 16
drwxrwxr-x 2 hellbroone-picoctf hellbroone-picoctf   61 Mar  1 22:51 .
drwxr-xr-x 5 hellbroone-picoctf hellbroone-picoctf 4096 Mar  1 22:38 ..
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf 1278 Mar 16  2023 code.py
-rwxrwxr-x 1 hellbroone-picoctf hellbroone-picoctf   27 Mar 16  2023 codebook.txt
-rw-rw-r-- 1 hellbroone-picoctf hellbroone-picoctf 1189 Mar 16  2023 convertme.py
hellbroone-picoctf@webshell:~/python$ chmod +x convertme.py
hellbroone-picoctf@webshell:~/python$ python convertme.py
If 94 is in decimal base, what is it in binary base?
Answer: 1011110
```
(Aqui tuve que usar un conversor de decimal a binario, para ello usé el de Rapidtables)
```
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
hellbroone-picoctf@webshell:~/python$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Aquí aprendimos a abrir un script desde python, pero en este caso, ejecutándolo con el comando de *python* para iniciar un script de python.
### Referencias
https://play.picoctf.org/practice/challenge/239
*Conversor de Decimal a Binario de [RapidTables]*: https://www.rapidtables.org/convert/number/decimal-to-binary.html