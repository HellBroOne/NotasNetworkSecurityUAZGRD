# Level 15
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.
**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al puerto 30001 en localhost mediante cifrado SSL.
**Nota útil: ¿Obtienes “HEARTBEATING” y “Read R BLOCK”? Utiliza -ign_eof y lee la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando...**
### Datos de Acceso al nivel
Comandos: ssh, telnet, nc, openssl, s_client, nmap
Usuario: bandit15
Contraseña: *jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt* (Nivel 15), *JQttfApK4SeyHwDlI9SXGR50qclOAil1* (Nivel 16)
Servidor: bandit.labs.overthewire.org
Puerto: 2220
### Solución
(Después de haber hecho lo del nivel 15)
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
...
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 18 10:53:16 2024 GMT; NotAfter: Feb 18 10:54:16 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEcjY6OTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjE4MTA1MzE2WhcNMjQwMjE4MTA1NDE2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCz
TX1NLedZhpQfXiWbWWD2BlNYjANpj+TnzUOI9ZbKJnOQJAbFfWZLA6No7XOStgje
+RPIoAHrX42G95VDfWtRms+qCsCTlUaS9291dZJQ3iOjBIE+PvmRcGdUlFJXDYa6
E61L2DKLbb8YSAnSuUPG3K7CtdxJpA5DpCBCmHEA9t5gZ5HGo9Gt9Kay9lhApX78
ocytwwHG15LplXI6LQB3ykhyCAcfljR3azd90T83dz7kLyM7yIMt60k1kemuX6RW
qSvkCvxmckRFoQPjwKZUopGLlhcC58Kb2xlwEGK+9j/ibBRkmEdBkOOeb5pJol7K
Wkd9LdG0nTWrggni7EKbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCA
j53OECoyjZMkHINZj35xk2kKQc9Jj9XjoCE0HlooUWd1ETik/2TkIbdWenozDrgH
10Jqmu/zAEhQkfFALBXCR7Vo0319yvR3rlnC2TdzMeBeUQ/n6ivPsCCL6SF8UTWT
XZJoTEfmp+Ma4zup/mEs23uO/FQ0J3LmSgICtXzPCA09M/ffj2UgTENdTHDltQxl
nQpzF+U40+bg/2PQ83XOTQJbZVbU2FnP/MitSYycxemLJXzbdsIxQhQy0VmTY73E
ZFemHVTbzEzcsCJRak4AyPZ9Zpi2uozHA8r1PqtnDzsN5FBFwuJxCuc+F8QeHh9e
QoyfsotkA6BO0LBqWNvE
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 39F52795D756FFD6A8C4ABCE083B1C5802953D8B9604896B6F4902A9B529B713
    Session-ID-ctx:
    Resumption PSK: 35A5A04750FC72AC2F7FE3AEDC5AAA2FB65FEE8CA162049C6D51D58CC1462970D02133BDF6955BE7CDF94D6F5D5A4897
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - 6d 28 04 58 b8 de 60 14-91 72 f3 ba ad 1f 75 38   m(.X..`..r....u8
    0020 - ac 24 85 4a 75 61 e6 60-c2 92 2d 8e 5a 2d 80 f9   .$.Jua.`..-.Z-..
    0030 - 52 4e 84 bb 76 bb e0 08-8b 44 6e e3 f6 6a 40 e8   RN..v....Dn..j@.
    0040 - 38 3f ba f0 db 49 82 30-fb 5b 82 3f 1b 2a be f4   8?...I.0.[.?.*..
    0050 - 5c da ba fd 88 23 c6 15-27 f9 82 08 0a b2 d4 2e   \....#..'.......
    0060 - fc 3a 70 2b 87 a4 cf 2c-ab 73 24 e5 c3 5a 1b 8a   .:p+...,.s$..Z..
    0070 - 8d 42 78 47 4f 32 b5 5e-48 8c 5b 73 9c 73 d4 19   .BxGO2.^H.[s.s..
    0080 - c7 70 28 40 61 5c 39 70-78 e2 59 68 25 77 f9 ef   .p(@a\9px.Yh%w..
    0090 - 63 b4 ed d9 8e 83 5d ae-d7 43 35 a5 18 18 01 40   c.....]..C5....@
    00a0 - 0e 6f 5f f5 43 f2 01 43-67 66 76 13 59 47 24 26   .o_.C..Cgfv.YG$&
    00b0 - 4b b9 0a db 45 78 7d 5c-e4 47 88 d2 a4 98 18 32   K...Ex}\.G.....2
    00c0 - 76 68 b5 52 49 3e 62 16-68 14 9f e2 87 48 82 91   vh.RI>b.h....H..

    Start Time: 1708381565
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
.... [etc.]
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.

C:Users/User> ssh bandit16@bandit.labs.overthewire.org -p 2220
Enter password: JQttfApK4SeyHwDlI9SXGR50qclOAil1
```
### Notas Adicionales
Para este nivel nos conectamos mediante ssl, que es una biblioteca de software para aplicaciones que proporcionan comunicaciones seguras a través de redes informáticas contra escuchas ilegales e identifican a la parte en el otro extremo.
**openssl:** Usar la herramienta ssl mediante el bash de linux.
### Referencias
https://overthewire.org/wargames/bandit/bandit16.html