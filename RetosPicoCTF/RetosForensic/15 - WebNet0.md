## Descripcion
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

Encontramos esto [captura de paquete](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) y [clave](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico .llave). Recuperar la bandera.
### Pistas
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

1. Intente utilizar una herramienta como Wireshark.
2. ¿Cómo se puede descifrar la transmisión TLS?
### Solución
```
1. Para esto tuvimos que usar SharkWire, para poder revisar los paquetes que se tengan en un archivo
2. Abrimos el paquete proporcionado desde el menú
3. Buscamos el stream 6 con paquetes UDP, para ello escribimos "udp.stream eq 6"
4. En el paquete 75 se encuentra nuestra bandera
```
### Notas Adicionales
**Wireshark** (antes conocido como Ethereal) es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica. Cuenta con todas las características estándar de un analizador de protocolos de forma únicamente hueca.
### Referencias
https://play.picoctf.org/practice/challenge/30