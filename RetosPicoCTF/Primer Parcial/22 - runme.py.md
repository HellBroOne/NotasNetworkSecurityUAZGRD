## Descripcion
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.

Ejecute el script `runme.py` para obtener la bandera. Descargue el script con su navegador o con `wget` en el webshell.
### Pistas
1. If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
2. To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
3. Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
4. Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 runme.py` You should have the flag now!
### Solución
```
hellbroone-picoctf@webshell:~$ cd python
hellbroone-picoctf@webshell:~/python$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-03-02 04:40:15--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                       100%[===================================================================================================>]     270  --.-KB/s    in 0s      

2024-03-02 04:40:15 (111 MB/s) - 'runme.py' saved [270/270]

hellbroone-picoctf@webshell:~/python$ python runme.py
picoCTF{run_s4n1ty_run}
hellbroone-picoctf@webshell:~/python$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel simplemente usamos un script que nos da la bandera, solo había que ejecutarlo y listo, no había mucha ciencia.

### Referencias
https://play.picoctf.org/practice/challenge/250