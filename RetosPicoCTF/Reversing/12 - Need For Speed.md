## Descripcion
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed).

El nombre del juego es [velocidad](https://www.youtube.com/watch?v=8piqd2BWeGI). ¿Eres lo suficientemente rápido para resolver este problema y mantenerlo por encima de las 50 mph? [necesidad de velocidad] (https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed).
### Pistas
1. What is the final key?

1. ¿Cuál es la clave final?
### Solución
```
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ wget https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed
--2024-04-30 13:25:46--  https://jupiter.challenges.picoctf.org/static/cd51b2c95be9f3626db6fe6665afb5a3/need-for-speed
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8888 (8.7K) [application/octet-stream]
Saving to: ‘need-for-speed’

need-for-speed               100%[==============================================>]   8.68K  --.-KB/s    in 0s      

2024-04-30 13:25:49 (105 MB/s) - ‘need-for-speed’ saved [8888/8888]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ chmod +x ./rev 
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ chmod +x ./need-for-speed                                                                         
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ gdb need-for-speed  
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
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) Quit
(gdb) quit
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ gdb -q need-for-speed
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) dissasemble main
Undefined command: "dissasemble".  Try "help".
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   %rbp
   0x000000000000091b <+1>:     mov    %rsp,%rbp
   0x000000000000091e <+4>:     sub    $0x10,%rsp
   0x0000000000000922 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000000925 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000000929 <+15>:    mov    $0x0,%eax
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    $0x0,%eax
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    $0x0,%eax
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    $0x0,%eax
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    $0x0,%eax
   0x0000000000000956 <+60>:    leave
   0x0000000000000957 <+61>:    ret
End of assembler dump.
(gdb) break *(main+30)
Breakpoint 1 at 0x938
(gdb) run
Starting program: /home/loro/need4speed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 1, 0x0000555555400938 in main ()
(gdb) break *(main+35)
Breakpoint 2 at 0x55555540093d
(gdb) jump *(main+35)
Continuing at 0x55555540093d.

Breakpoint 2, 0x000055555540093d in main ()
(gdb) run
The program being debugged has been started already.
Start it from the beginning? (y or n) y
Starting program: /home/loro/need4speed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 1, 0x0000555555400938 in main ()
(gdb) jump *(main+35)
Continuing at 0x55555540093d.

Breakpoint 2, 0x000055555540093d in main ()
(gdb) quit
A debugging session is active.

        Inferior 1 [process 41531] will be killed.

Quit anyway? (y or n) y
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/need4speed]
└─$ gdb -q need-for-speed
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   %rbp
   0x000000000000091b <+1>:     mov    %rsp,%rbp
   0x000000000000091e <+4>:     sub    $0x10,%rsp
   0x0000000000000922 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000000925 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000000929 <+15>:    mov    $0x0,%eax
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    $0x0,%eax
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    $0x0,%eax
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    $0x0,%eax
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    $0x0,%eax
   0x0000000000000956 <+60>:    leave
   0x0000000000000957 <+61>:    ret
End of assembler dump.
(gdb) break *(main+30)
Breakpoint 1 at 0x938
(gdb) rn
Target exec does not support this command.
(gdb) run
Starting program: /home/loro/need4speed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 1, 0x0000555555400938 in main ()
(gdb) jump *(main+35)
Continuing at 0x55555540093d.
Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #24c43740 speeding along!}
[Inferior 1 (process 42113) exited normally]
(gdb) 

```
### Notas Adicionales
Muy buen juego el Need For Speed.
### Referencias
https://play.picoctf.org/practice/challenge/39