## Descripción
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/238/atbash.jpg).

¿Qué tal un poco de las escondidas, je? Mira esta imagen [aquí](https://artifacts.picoctf.net/c/238/atbash.jpg).
### Pistas
1. Download the image and try to extract it.

1. Descarga la imagen e intenta extraerla.
### Solución
```
┌──(loro㉿KaliLinux)-[~/hidetosee]
└─$ sudo apt install steghide                             
[sudo] password for loro: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libmcrypt4 libmhash2
Suggested packages:
  libmcrypt-dev mcrypt
The following NEW packages will be installed:
  libmcrypt4 libmhash2 steghide
0 upgraded, 3 newly installed, 0 to remove and 493 not upgraded.
Need to get 92.4 kB/309 kB of archives.
After this operation, 905 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-9+b1 [92.4 kB]
Fetched 92.4 kB in 6s (15.4 kB/s)                       
Selecting previously unselected package libmcrypt4.
(Reading database ... 403885 files and directories currently installed.)
Preparing to unpack .../libmcrypt4_2.5.8-7_amd64.deb ...
Unpacking libmcrypt4 (2.5.8-7) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../libmhash2_0.9.9.9-9+b1_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-9+b1) ...
Selecting previously unselected package steghide.
Preparing to unpack .../steghide_0.5.1-15_amd64.deb ...
Unpacking steghide (0.5.1-15) ...
Setting up libmhash2:amd64 (0.9.9.9-9+b1) ...
Setting up libmcrypt4 (2.5.8-7) ...
Setting up steghide (0.5.1-15) ...
Processing triggers for libc-bin (2.37-12) ...
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/hidetosee]
└─$ ls
atbash.jpg
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/hidetosee]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/hidetosee]
└─$ cat encrypted.txt                                                       
krxlXGU{zgyzhs_xizxp_8z0uvwwx}

[VAMOS A CYBERCHEF]
1. Pegamos la cadena de "krxlXGU{zgyzhs_xizxp_8z0uvwwx}"
2. Desdencriptamos Atbash Cipher
3. La bandera es picoCTF{atbash_crack_8a0feddc}
```
### Notas Adicionales
The Atbash cipher is **a monoalphabetical substitution cipher that replaces each letter with its symmetrical one in the alphabet**. It is believed to be the first cipher ever used, and its use pre-dates Egyptian examples of encryption.
### Referencias
https://play.picoctf.org/practice/challenge/251
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)
