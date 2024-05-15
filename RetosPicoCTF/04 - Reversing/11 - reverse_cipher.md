## Descripción
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag?

Hemos recuperado un [binario](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) y un [archivo de texto](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this ). ¿Puedes revertir la bandera?
### Pistas
1. objdump and Gihdra are some tools that could assist with this

1. objdump y Gihdra son algunas herramientas que podrían ayudar con esto
### Solución
```
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
--2024-04-30 12:48:20--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: ‘rev’

rev                          100%[==============================================>]  16.46K  --.-KB/s    in 0s      

2024-04-30 12:48:31 (60.4 MB/s) - ‘rev’ saved [16856/16856]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
--2024-04-30 12:48:38--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: ‘rev_this’

rev_this                     100%[==============================================>]      24  --.-KB/s    in 0s      

2024-04-30 12:48:48 (22.8 MB/s) - ‘rev_this’ saved [24/24]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ cat rev_this               
picoCTF{w1{1wq85jc=2i0<}                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ cat rev                                                                                     
ELF>�@X:@8
          @@@@h���xx==   ���-�=�=px�-�=�=����DDP�tdx x x <<Q�tdR�td�-�=�=▒▒/lib64/ld-linux-x86-64.so.2GNUGNUR=Q�<v�o�ԯ���Y3�
        �
         �e�m[ (!w 
                   � ."libc.so.6exitfopenputsfputcfclosefread__cxa_finalize__libc_start_mainGLIBC_2.2.5_ITM_deregisterTMCloneTable__gmon_start___ITM_registerTMCloneTableu▒i        O���@PP@�?�?�?�?
�?
  ▒@ @(@0@8@@   H�H��/H��t��H���5�/�%�/@�%�/h������%�/h������%�/h������%�/h������%�/h������%�/h������%b/f�1�I��^H��HH�=��/�DH�=�/H�z/H9�tH��.H��t   �����H�=Q/H�5J/H)�H��H��H��?H�H��tH��.H����fD���=/u/UH�=�.H��t
                                                                                              H�=�.�-����h�����.]�����{���UH��H��PH�5tH�=o�����H�E�H�5hH�=c�����H�E�H�}�u
                                                     H�=W�b���H�}�u
                                                                   H�=~�O���H�U�H�E�H�Ѻ�▒H���B����E܃}�
��o����E��#�E�H��D��E��E�H�U�H�։��'����E��}�~��E�C�E�H��D��E��E�����u
                                                                     �E����E��
�E����E��E�H�U�H�։�������E��}�~��EǈE��E�H�U�H�։������H�E�H�������H�E�H�����������AWI��AVI��AUA��ATL�%+UH�-+SL)�H�����H��t�L��L��D��A��H��H9�u�H�[]A\A]A^A_��H�H��rflag.txtarev_thisNo flag found, please make sure this is run on the se����X��������0zRxis on the server<�����▒����(���X
                ����+zRx
                       $▒���pF▒J
?                               �?▒;*3$"D`��\=���DA�C
D|h���]B�E▒�E �E(�H0�H8�G@j8A0A(B B▒B������@
4�▒����P0
�
 ▒@���  ▒���������o���o����o�=6FVfv�P@GCC: (Debian 8.2.0-14) 8.2.0��0P� (
�

��4 x � �=�=�=�?@▒H@X@▒��
                         �!@7X@F�=m�y�=�������!����=��=��=�x �@�
                                                                0 � ▒H@.@S▒X@Z
                                                                              4n��▒H@� �▒P@� ��]�`@��+�X@��D�
                                                                                                             ▒X@* D"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.7325__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryrev.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5fread@@GLIBC_2.2.5_edatafclose@@GLIBC_2.2.5fputc@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmainfopen@@GLIBC_2.2.5exit@@GLIBC_2.2.5__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.ABI-tag.note.gnu.build-id.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.got.plt.data.bss.comment�#�� 1��$D��No
         00▒VPP�^���o��▒k��z((▒�B��▒��  p�����44        �  �x x <�� ������=�-��?��@�H@HX@X�0X0x0x▒      �6`P9                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ chmod +x ./rev 
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ ./rev          
No flag found, please make sure this is run on the server
zsh: segmentation fault  ./rev
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ nano pyrev.py
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ python pyrev.py
Traceback (most recent call last):
  File "/home/loro/revcipher/pyrev.py", line 5, in <module>
    flag += ord(d[j])-5
TypeError: can only concatenate str (not "int") to str
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ nano pyrev.py  
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ python pyrev.py
kk^q>VA}r3v3rs37ee84d27
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ nano pyrev.py  
                                                                                                                    
[YA USANDO GHIDRA SABEMOS QUE LA BANDERA ESTA ENCRIPTADA, POR ELLO VAMOS A ENTRAR A NANO]
GNU nano 7.2                                          pyrev.py                                                    
d = open("rev_this").read()
flag = ""
for j in range(8,23):
        if j & 1 == 0:
                flag += chr( ord(d[j])-5 )
        else:
                flag += chr( ord(d[j])+2 )
print(flag)

[SALIMOS Y GUARDAMOS DE NANO]
┌──(loro㉿KaliLinux)-[~/revcipher]
└─$ python pyrev.py
r3v3rs37ee84d27

```
### Notas Adicionales
Ghidra es una herramienta de ingeniería inversa gratuita y de código abierto desarrollada por la Agencia de Seguridad Nacional (NSA) de los Estados Unidos. Los binarios se publicaron en la conferencia RSA en marzo de 2019; las fuentes se publicaron un mes después en GitHub.
### Referencias
https://play.picoctf.org/practice/challenge/79