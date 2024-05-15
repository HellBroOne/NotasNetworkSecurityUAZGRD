## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

¿Puedes averiguar qué hay en el registro `eax` ? Coloque su respuesta en el formato de bandera picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su indicador sería `picoCTF{17}`. Descargue el volcado del ensamblado [aquí](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
### Pistas
1. As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

1. Como ocurre con la mayoría de los ensamblajes, hay mucho ruido en el volcado de instrucciones. Encuentre la única línea que pertenece a esta pregunta y ¡no lo dude!
### Solución
```
┌──(loro㉿KaliLinux)-[~/bit-o-asm/1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-05-14 21:21:34--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.32, 18.154.132.88, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt                                   100%[========================================================================================================================================>]     209  --.-KB/s    in 0s      

2024-05-14 21:21:35 (118 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/1]
└─$ head disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/1]
└─$ cat disassembler-dump0_a.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/1]
└─$ mousepad disassembler-dump0_a.txt 
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/1]
└─$ python                  
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30",16))
48

La bandera es: picoCTF{48}
```
### Notas Adicionales
EAX, AX, AH, AL: Llamado registro acumulador. Se utiliza para acceso a puertos de E/S, aritmética, llamadas de interrupción, etc.
### Referencias
https://play.picoctf.org/practice/challenge/391