## Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

El uso de tabcomplete en la Terminal agregará años a tu vida, especialmente. cuando se trata de estructuras de directorios y nombres de archivos largos y confusos: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)
### Pistas
1. After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
--2024-03-01 04:43:37--  https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4521 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                           100%[===================================================================================================>]   4.42K  --.-KB/s    in 0s      

2024-03-01 04:43:37 (1.66 GB/s) - 'Addadshashanammu.zip' saved [4521/4521]

hellbroone-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  flag  warm  warm.1
hellbroone-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
hellbroone-picoctf@webshell:~$ ls 
.bash_history         .bashrc               .wget-hsts            Addadshashanammu.zip  flag                  warm.1                
.bash_logout          .profile              Addadshashanammu/     README.txt            warm                  
hellbroone-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
hellbroone-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
8#TT 1tt$DNpicoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ cat fang-of-haynekhtnamet 
0)@/lib6(;Cmon_start___ITM_registerTMCloneTableui  1
 @%
H=1I^HHPTLH
 DH=
 UH
 H9HtHZ
]f.]@f.H=i
 H5b
 UH)HHHH?HHtH!
 Ht
   ]f]@f.=
 u/H=    UHt
H        ]fDUH]fUHH=]f.DAWAVIAUATL%F UH-F SAIL)HWHt 1LLDAHH9u[]A\A]A^A_Ðf.*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70} <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<< (BANDERA)
X"H0zRx
                                                                                                                               Rx
                                                                                                                                 FJ
R                                                                                                                                  ?;*3$"D\RAC
D|XeBBE B(H0H8M@r8A0A(B BB0
o`

 GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.08Tt`


    
  $ z  @R Yx  `e ~0+ :  "
                         crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.7698__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryfang-of-haynekhtnamet.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5_edata__libc_start_main@@GLIBC_2.2.
                         picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ exit
logout
Webshell session has ended.
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/176