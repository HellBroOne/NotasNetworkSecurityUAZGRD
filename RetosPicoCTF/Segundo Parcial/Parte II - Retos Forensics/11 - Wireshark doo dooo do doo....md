## Descripción
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).

¿Puedes encontrar la bandera? [tiburón1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).
### Pistas
(None)

(Ninguna)
### Solución
```
1. Descargamos el archivo
2. Abrimos el archivo con Wireshark, y vemos los streams
3. Escribimos en el filtrador "tcp.stream eq 5"
4. Buscamos en los stream y encontramos la bandera en el Stream #827
5. El final del stream 
6. La bandera es: picoCTF{p33kab00_1_s33_u_deadbeef}
```
### Notas Adicionales


### Referencias
https://play.picoctf.org/practice/challenge/115