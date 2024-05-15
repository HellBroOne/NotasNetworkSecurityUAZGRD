## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

¿Puedes averiguar qué hay en el registro `eax` ? Coloque su respuesta en el formato de bandera picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su indicador sería `picoCTF{17}`. Descargue el volcado del ensamblado [aquí](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).
### Pistas
1. Not everything in this disassembly listing is optimal.

1. No todo lo que aparece en este listado de desmontaje es óptimo.
### Solución
```
┌──(loro㉿KaliLinux)-[~/bit-o-asm/3]
└─$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
--2024-05-14 21:40:15--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.74, 18.154.132.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 461 [application/octet-stream]
Saving to: ‘disassembler-dump0_c.txt’

disassembler-dump0_c.txt                                   100%[========================================================================================================================================>]     461  --.-KB/s    in 0s      

2024-05-14 21:40:16 (410 MB/s) - ‘disassembler-dump0_c.txt’ saved [461/461]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/3]
└─$ cat disassembler-dump0_c.txt                 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/3]
└─$ python
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x9fe1a",16))
654874
>>> print(int("0x4",16))
4
>>> 654874*4
2619496
>>> print(int("0x1f5",16))
501
>>> 2619496+501
2619997

La bandera es: picoCTF{2619997}
```
### Notas Adicionales
La instrucción "imul" indica el producto entre el elemento en EAX * src, siendo src un entero
### Referencias
https://play.picoctf.org/practice/challenge/393