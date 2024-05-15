## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

Encontramos esta [captura de paquetes](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recupera la bandera que fue sustraída de la red.
### Pistas
(None)

(Ninguna)
### Solución
```
(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2]$ wget 'https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap'

--2024-03-19 15:03:52--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’
capture.pcap          100%[=======================>] 109.69K  --.-KB/s    in 0.1s    
2024-03-19 15:03:52 (832 KB/s) - ‘capture.pcap’ saved [112318/112318]

  
(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2]$ ls    
capture.pcap

(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2]$ file capture.pcap                        
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2]$ wireshark capture.pcap &
[1] 32889
(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2]$ ls
capture.pcap  datos.txt
(kali㉿kali)-[~/picoctf/forensic/parte2/sharkonwire2] $ cat datos.txt | grep UDP  | awk '{print $7}' | cut -c2- | grep -v 000
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125

[EN CYBERCHEF]
1. Codificamos desde ASCII
2. Obtenemos la bandera: picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
### Notas Adicionales
**Wireshark** (antes conocido como Ethereal) es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica. Cuenta con todas las características estándar de un analizador de protocolos de forma únicamente hueca.
### Referencias
https://play.picoctf.org/practice/challenge/84