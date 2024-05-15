## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

¿Puedes averiguar qué hay en el registro `eax` ? Coloque su respuesta en el formato de bandera picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su indicador sería `picoCTF{17}`. Descargue el volcado del ensamblado [aquí](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
### Pistas
1. Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
2. Of course, if you're really good, you'll only need one attempt to solve this problem.

1. No le digas a nadie que te dije esto, pero puedes resolver este problema sin comprender la relación de comparación/salto.
2. Por supuesto, si eres realmente bueno, sólo necesitarás un intento para resolver este problema.
### Solución
```
┌──(loro㉿KaliLinux)-[~/bit-o-asm/4]
└─$ wget https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
--2024-05-14 21:56:39--  https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.108, 18.154.132.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 482 [application/octet-stream]
Saving to: ‘disassembler-dump0_d.txt’

disassembler-dump0_d.txt                                   100%[========================================================================================================================================>]     482  --.-KB/s    in 0s      

2024-05-14 21:56:40 (2.52 MB/s) - ‘disassembler-dump0_d.txt’ saved [482/482]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/4]
└─$ python
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x65",16))
101
>>> print(int("0x9fe1a",16))
654874
>>> print(int("0x2710",16))
10000
>>> 654874-101
654773

La bandera es: picoCTF{654773}
```
### Notas Adicionales
cmp compara la diferiencia al igual que sub, sin embargo, en cmp no se guarda la diferiencia y en sub si.
### Referencias
https://play.picoctf.org/practice/challenge/394