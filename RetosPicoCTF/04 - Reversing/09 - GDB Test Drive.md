## Descripción
Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:
- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

¿Puedes conseguir la bandera? Descargue este [binario](https://artifacts.picoctf.net/c/87/gdbme). Aquí están las instrucciones de prueba de manejo:
- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `conjunto de diseño (gdb)`
- `(gdb) ruptura *(principal+99)`
- `(gdb) ejecutar`
- `(gdb) salto *(principal+104)`
### Pistas
(None)

(Ninguna)
### Solución
```
┌──(loro㉿KaliLinux)-[~]
└─$ mkdir gdbtest     
                                                                                                                   
┌──(loro㉿KaliLinux)-[~]
└─$ cd gdbtest 
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ wget https://artifacts.picoctf.net/c/87/gdbme                                                      
--2024-04-30 12:16:33--  https://artifacts.picoctf.net/c/87/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: ‘gdbme’

gdbme                        100%[=============================================>]  16.65K  --.-KB/s    in 0.003s  

2024-04-30 12:16:42 (4.98 MB/s) - ‘gdbme’ saved [17048/17048]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ ls    
gdbme
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ ./gdbme
zsh: permission denied: ./gdbme
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ chmod +x gdbme
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ ./gdbme       
^C
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ chmod +x gdbme 
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ gdb gdbme            
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
                                                                                                                    
[EN LAYAOUT ESCRIBIMOS LOS COMANDOS SIGUIENTES]
(gdb) layout asm
(gdb) break *(main+99)
(gdb) run
(gdb) jump *(main+104)
[COPIAMOS LA BANDERA]
┌──(loro㉿KaliLinux)-[~/gdbtest]
└─$ echo "picoCTF{d3bugg3r_dr1v3_7776d758}"
picoCTF{d3bugg3r_dr1v3_7776d758}
```
### Notas Adicionales
GDB o GNU Debugger es el depurador estándar para el compilador GNU. Es un depurador portable que se puede utilizar en varias plataformas Unix y funciona para varios lenguajes de programación como C, C++ y Fortran. GDB fue escrito por Richard Stallman en 1986.
### Referencias
https://play.picoctf.org/practice/challenge/273