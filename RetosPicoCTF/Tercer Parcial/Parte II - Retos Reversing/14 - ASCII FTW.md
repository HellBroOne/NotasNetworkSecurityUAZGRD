## Descripción
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program. You can download the file from [here](https://artifacts.picoctf.net/c/507/asciiftw).

Este programa ha construido la bandera utilizando valores hexadecimales ascii. Identifique el texto de la bandera desmontando el programa. Puede descargar el archivo desde [aquí](https://artifacts.picoctf.net/c/507/asciiftw).
### Pistas
1. The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
2. Online hex-ascii converters can be helpful.

1. El rango combinado de hex-ascii para alfabetos ingleses y dígitos numéricos es de 30 a 7A.
2. Los convertidores hex-ascii en línea pueden resultar útiles.
### Solución
```
┌──(loro㉿KaliLinux)-[~/asciiftw]
└─$ wget https://artifacts.picoctf.net/c/507/asciiftw                                         
--2024-05-14 20:16:12--  https://artifacts.picoctf.net/c/507/asciiftw
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.32, 18.154.132.88, 18.154.132.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16752 (16K) [application/octet-stream]
Saving to: ‘asciiftw’

asciiftw                                                   100%[========================================================================================================================================>]  16.36K  --.-KB/s    in 0s      

2024-05-14 20:16:13 (216 MB/s) - ‘asciiftw’ saved [16752/16752]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/asciiftw]
└─$ cat asciiftw         
@@@@�▒▒▒XX��   pp�-�=�=`h�-�=�=�888 XXXDDS�td888 P�td      DDQ�tdR�td�-�=�=PP/lib64/ld-linux-x86-64.so.2GNU�GNU_M1�v���+8��z}�e��GNU��e�mZ 
                                                                                                                                           2v � #"libc.so.6__stack_chk_failprintf__cxa_finalize__libc_start_mainGLIBC_2.2.5GLIBC_2.4_ITM_der�H�=��2/��H�=Y/H�R/H9�tH�/H��t�������H�=)/H�5"/H)�H��H��?H��H�H��tH��.H����fD�����=�.u+UH�=�.H��t��H���PTL�H�
                                                                                                 H�=�.� ����d�����.]������w�����UH��H��0dH�%(H�E�1��E�p�E�i�E�c�E�o�E�C�E�T�E�F�E�{�E�A�E�S�E�C�E�I�E�I�E�_�E�I�E�S�E�_�E�E�E�A�E�S�E�Y�E�_���V����H�E�dH3%(t�1�����f.�D��AWL�=c+AVI��AUI��ATA��UH�-T+SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��The flag starts with %x
D���x0����@����`���`I���� ��������8zRx
                                     ����/D$4����0F▒J
�                                                    �?▒:*3$"\����t���� �q����E�C
D�(���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�P���` 
��▒����o���
�
 ▒�?0(� ������o8���o���o(���o�=0@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|��(      8
h
 (
 P`��   h �=�=�=▒�?@▒@�
                       ��! 7▒@F�=m`y�=������l!����=��=��=�  �▒�?�
                                                                 � � @3@�:Vj�@� @� �@e�▒▒@��/�▒@�i��@�"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryasciiftw.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTable_edata__stack_chk_fail@@GLIBC_2.4printf@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
�  �    D�h ������=�-��?�@0                                                                                                                                                               ��▒i���q���o((~���o88�hh▒�B((0▒�  0�PP�`` ���5���
                         @00+@00▒       p6$�8▒  
[VAMOS A GHIDRA PARA HACER INGENIERIA INVERSA]
1. Abrimos un proyecto nuevo.
2. Importamos el archivo de "asciiftw"
3. Se hace ingenieria inversa al archivo.
4. Hacemos clic en "Display Script Manager"
5. Creamos un nuevo script en "Create New Script"
6. Usamos el siguiente script, proporcionado en la segunda referencia:
	from ghidra.program.model.mem import MemoryAccessException 
	start_addr = currentProgram.getAddressFactory().getAddress("00101184") 
	end_addr = currentProgram.getAddressFactory().getAddress("001011fc") 
	byte_list = [] 
	current_addr = start_addr 
	while current_addr <= end_addr: 
		instruction = getInstructionAt(current_addr) 
			if instruction is not None: 
				operand = instruction.getOpObjects(1)[0] 
				# get second operand 
				byte_val = operand.getValue() & 0xFF 
				# convert to unsigned byte 
				byte_list.append(byte_val) 
				
				current_addr = current_addr.next() 
	flag = list(map(chr, byte_list)) 
	print("Flag:", "".join(flag))
Este script lo que hace es obtener la bandera de los caracteres ASCII que se construyen en el archivo binario de ensamblador, juntandolas y creando la bandera final:
7. Hacemos clic en "Run Script"
8. Se nos da la bandera final: ('Flag:', 'picoCTF{ASCII_IS_EASY_7BCD971D}')
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/389
***How To Crack PicoCTF ASCII FTW With Ghidra:*** https://www.stackzero.net/picoctf-ascii-ftw/