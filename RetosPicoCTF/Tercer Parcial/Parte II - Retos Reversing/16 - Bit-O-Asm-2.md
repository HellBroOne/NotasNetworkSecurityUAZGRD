## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

¿Puedes averiguar qué hay en el registro `eax` ? Coloque su respuesta en el formato de bandera picoCTF: `picoCTF{n}` donde `n` es el contenido del registro `eax` en la base numérica decimal. Si la respuesta fuera `0x11` su indicador sería `picoCTF{17}`. Descargue el volcado del ensamblado [aquí](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
### Pistas
1. `PTR`'s or 'pointers', reference a location in memory where values can be stored.

1. Los `PTR` o 'punteros' hacen referencia a una ubicación en la memoria donde se pueden almacenar los valores.
### Solución
```
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2024-05-14 21:34:24--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.74, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt                                   100%[========================================================================================================================================>]     270  --.-KB/s    in 0s      

2024-05-14 21:34:24 (274 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ cat disassembler-dump0_b.txt | grep "eax"
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ echo "hasta el momento eax contiene lo del puntero [rbp-0x4], entonces lo que se haya asignado a ese puntero es lo que contiene el registro eax"
hasta el momento eax contiene lo del puntero [rbp-0x4], entonces lo que se haya asignado a ese puntero es lo que contiene el registro eax
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ cat disassembler-dump0_b.txt | grep "[rbp-0x4]"                                                                                                 
grep: Invalid range end
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ cat disassembler-dump0_b.txt | grep "rbp-0x4"  
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/bit-o-asm/2]
└─$ python
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x9fe1a",16))
654874

La bandera es: picoCTF{654874}
```
### Notas Adicionales
Los punteros (PTR) hacen referencia al espacio de memoria al cual se están siendo apuntados.
### Referencias
https://play.picoctf.org/practice/challenge/392