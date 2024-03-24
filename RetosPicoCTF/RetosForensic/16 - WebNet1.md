## Descripcion
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

Encontramos esta [captura de paquete](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) y la [clave](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico .llave). Recupera la bandera.
### Pistas
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

1. Intente utilizar una herramienta como Wireshark.
2. ¿Cómo se puede descifrar la transmisión TLS?
### Solución
```
1. Para esto tuvimos que usar SharkWire, para poder revisar los paquetes que se tengan en un archivo
2. Abrimos el paquete proporcionado desde el menú
3. Seguimos el rastro TLC, haciendo clic derecho y en "Seguir" > "TLS Stream"
4. No aparece nada, sin embargo, hay que entrar a la pestaña "Editar" en la parte de "Preferencias".
5. Se nos abre una ventana, pero hay que entrar a dónde dice Protocolos y vamos a la sección de "TLS"
6. Hacemos clic en editar "RSA Keys" para poder agregar una clave RSA.
7. Pulsamos el botón "+" y cargamos la llave.
8. Hay que buscar en los paquetes a la cadena que diga "picoCTF"
9. Vamos a "Editar" y en "Buscar Siguiente" y escribimos "picoCTF"
10. Nos aparecerá un paquete 55
11. En el paquete 55, hacemos clic derecho y seguimos el Stream "TLS"
12. Nos aparecera un texto visible desencriptado con la bandera de: picoCTF{honey.roasted.peanuts}
```
### Notas Adicionales
**Wireshark** (antes conocido como Ethereal) es un analizador de protocolos utilizado para realizar análisis y solucionar problemas en redes de comunicaciones, para análisis de datos y protocolos, y como una herramienta didáctica. Cuenta con todas las características estándar de un analizador de protocolos de forma únicamente hueca.
Las llaves RSA sirven para poder obtener una desencriptación del tráfico de una captura de paquetes y poder ver que es lo que se conectó en la red.
### Referencias
https://play.picoctf.org/practice/challenge/42