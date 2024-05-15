## Descripción
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".

¿Puedes descifrar este mensaje? Descifre este [mensaje](https://artifacts.picoctf.net/c/158/cipher.txt) usando esta clave "CYLAB".
### Pistas
1. https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher
### Solución
```
1. Descargamos el archivo txt del reto.
2. Hacemos cat y nos sale lo siguiente:
	rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}
3. Vamos a CyberChef y ponemos en la receta a Vigenere Decode.
4. Ingresamos la palabra clave de "CYLAB".
5. La bandera resultante es: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/316
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)