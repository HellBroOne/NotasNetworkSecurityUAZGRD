## Descripción
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

¿Puedes averiguar qué hay en el registro `eax` al final de la función `main` ? Coloque su respuesta en el formato de bandera picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su indicador sería `picoCTF{17}`. Desmonta [esto](https://artifacts.picoctf.net/c/512/debugger0_a).
### Pistas
1. gdb is a very good debugger to use for this problem and many others!
2. `main` is actually a recognized symbol that can be used with gdb commands.

1. ¡gdb es un muy buen depurador para este problema y muchos otros!
2. `main` es en realidad un símbolo reconocido que se puede usar con los comandos gdb.
### Solución
```
┌──(loro㉿KaliLinux)-[~/gdb-baby-steps/1]
└─$ wget https://artifacts.picoctf.net/c/512/debugger0_a                                               
--2024-05-15 10:02:56--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.74, 18.154.132.32, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16472 (16K) [application/octet-stream]
Saving to: ‘debugger0_a.1’

debugger0_a.1                100%[=============================================>]  16.09K  --.-KB/s    in 0.004s  

2024-05-15 10:02:58 (3.54 MB/s) - ‘debugger0_a.1’ saved [16472/16472]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdb-baby-steps/1]
└─$ chmod +x debugger0_a                                
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdb-baby-steps/1]
└─$ gdb debugger0_a
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
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
(gdb) dissasemble main
Undefined command: "dissasemble".  Try "help".
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
(gdb) q
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/gdb-baby-steps/1]
└─$ python
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x86342",16))
549698
>>> exit()


La bandera es picoCTF{549698}
```
### Notas Adicionales
dissasemble es un comando para desmontar o mostrar en completo la funcion que se especifique.
### Referencias
https://play.picoctf.org/practice/challenge/395