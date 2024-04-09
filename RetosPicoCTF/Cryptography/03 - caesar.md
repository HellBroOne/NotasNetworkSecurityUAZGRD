## Descripcion
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).

Descifre este [mensaje](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).
### Pistas
1. caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

1. cifrado César [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)
### Solución
```
1. Descargamos el mensaje del reto.
2. hacemos cat ciphertext
3. Nos da lo siguiente: picoCTF{dspttjohuifsvcjdpoabrkttds}
4. Desencriptamos en Cyberchef, esto esta encriptado en ROT13
5. Hay que rotar (en mi caso) -1 veces.
6. La bandera es: picoCTF{crossingtherubiconzaqjsscr}
```
### Notas Adicionales
El cifrado César, también conocido como cifrado por desplazamiento, es una de las formas más antiguas y sencillas de cifrar un mensaje.
Es un tipo de cifrado de sustitución en el que cada letra del mensaje original (que en criptografía se llama texto sin formato) se reemplaza con una letra correspondiente a un cierto número de letras desplazadas hacia arriba o hacia abajo en el alfabeto.
Para cada letra del alfabeto, tomaría su posición en el alfabeto, digamos 3 para la letra "C", y la cambiaría según el número clave. Si tuviéramos una clave de +3, esa "C" se cambiaría a una "F" y el mismo proceso se aplicaría a cada letra del texto sin formato.
De esta forma, un mensaje que inicialmente era bastante legible, acaba en una forma que no se puede entender a simple vista.
### Referencias
https://play.picoctf.org/practice/challenge/64
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)