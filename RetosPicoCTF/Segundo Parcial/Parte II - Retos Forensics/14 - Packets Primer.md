## Descripcion
Download the packet capture file and use packet analysis software to find the flag.
- [Download packet capture](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)

Descarga el archivo de captura de paquetes y utiliza un software de análisis de paquetes para encontrar la bandera.
- [Descargar captura de paquetes](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)
### Pistas
1. Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

1. Wireshark, si puedes instalarlo y usarlo, es probablemente el producto de software de análisis de paquetes más amigable para principiantes.
### Solución
```
1. Descargamos el archivo de captura de paquetes.
2. Lo abrimos con WireShark.
3. Elegimos un stream con protocolo de TCP (en este archivo todos lo tienen).
4. Hacemos clic derecho vamos a "Seguir" > "TCP Stream"
5. Se nos da la bandera: picoCTF{p4ck37_5h4rk_ceccaa7f}
```
### Notas Adicionales
**Wireshark** (antes conocido como Ethereal) es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica. Cuenta con todas las características estándar de un analizador de protocolos de forma únicamente hueca.
### Referencias
https://play.picoctf.org/practice/challenge/286