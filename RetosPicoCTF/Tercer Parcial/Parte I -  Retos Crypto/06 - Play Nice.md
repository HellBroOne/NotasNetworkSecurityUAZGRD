## Descripción
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 40742` [playfair.py](https://mercury.picoctf.net/static/283dcc58048f3a6ac83b4c11ec696954/playfair.py)

No todos los cifrados antiguos eran tan malos... La bandera no tiene el formato estándar. `nc mercury.picoctf.net 40742` [playfair.py](https://mercury.picoctf.net/static/283dcc58048f3a6ac83b4c11ec696954/playfair.py)
### Pistas
1. (None)

1. (Ninguna)
### Solución
```
┌──(loro㉿KaliLinux)-[~/play-nice]
└─$ nc mercury.picoctf.net 40742
Here is the alphabet: irlgektq8ayfp5zu037nov1m9xbc64shwjd2
Here is the encrypted message: h5a1sqeusdi38obzy0j5h3ift7s2r2
What is the plaintext message? si

Este es un tipo de cifrado "Playfair". 
Hacemos una matriz con el alfabeto obtenido para decifrar: 
	i r l g e k
	t q 8 a y f
	p 5 z u 0 3
	7 n o v 1 m
	9 x b c 6 4
	s h w j d 2
Aqui podemos ir a la siguiente pagina de "PlayFair Cipher" y pegamos el alfabeto abajo de la matriz.
En el cuadro de texto escribimos el mensaje encriptado.
Se nos da el mensaje de: xqyvhtg02jkplzo8eyhu25ktip2dkh

┌──(loro㉿KaliLinux)-[~/play-nice]
└─$ nc mercury.picoctf.net 40742
Here is the alphabet: irlgektq8ayfp5zu037nov1m9xbc64shwjd2
Here is the encrypted message: h5a1sqeusdi38obzy0j5h3ift7s2r2
What is the plaintext message? xqyvhtg02jkplzo8eyhu25ktip2dkh
Congratulations! Here's the flag: 25a0ea7ff711f17bddefe26a6354b2f3
La bandera es: 25a0ea7ff711f17bddefe26a6354b2f3, no esta en formato estandar.
```
### Notas Adicionales
El cifrado Playfair es una técnica de cifrado simétrico manual y fue el primer cifrado de sustitución de digramas literal.

La técnica cifra pares de letras (bigramas o digramas), en lugar de letras individuales como en el cifrado de sustitución simple y en los sistemas de cifrado Vigenère bastante más complejos que se utilizaban en ese momento.
### Referencias
https://play.picoctf.org/practice/challenge/114
***PlayFair Cipher:*** https://www.dcode.fr/playfair-cipher