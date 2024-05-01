## Descripcion
What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/291/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

¿Qué puedes hacer con este archivo? Olvidé la llave de mi caja fuerte, pero se supone que este [archivo](https://artifacts.picoctf.net/c/291/SafeOpener.class) me ayudará a recuperar la llave perdida. ¿Puedes ayudarme a desbloquear mi caja fuerte?
### Pistas
1. Download and try to decompile the file.

1. Descargue e intente descompilar el archivo.
### Solución
```
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/safeopener2]
└─$ wget https://artifacts.picoctf.net/c/291/SafeOpener.class
--2024-04-30 12:44:40--  https://artifacts.picoctf.net/c/291/SafeOpener.class
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2036 (2.0K) [application/octet-stream]
Saving to: ‘SafeOpener.class.1’

SafeOpener.class.1           100%[==============================================>]   1.99K  --.-KB/s    in 0s      

2024-04-30 12:44:49 (36.4 MB/s) - ‘SafeOpener.class.1’ saved [2036/2036]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/safeopener2]
└─$ java SafeOpener                                          
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter password for the safe: eso
ZXNv
Password is incorrect

You have  2 attempt(s) left
Enter password for the safe: tilin
dGlsaW4=
Password is incorrect

You have  1 attempt(s) left
Enter password for the safe: a
YQ==
Password is incorrect

You have  0 attempt(s) left
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/safeopener2]
└─$  

[VAMOS A UN DECOMPILADOR DE JAVA EN LINEA]
1. En el decompilador de Java tenemos un decompilador que nos permite de un archivo class mandarlo a codigo fuente.
2. Elegimos el SafeOpener.class y hacemos clic en upload and decompile
3. Se nos muestra el codigo y abajo sale la bandera
4. La bandera es picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_198203f7}
```
### Notas Adicionales

### Referencias
https://play.picoctf.org/practice/challenge/375
***Java Decompiler Online:*** http://www.javadecompilers.com/