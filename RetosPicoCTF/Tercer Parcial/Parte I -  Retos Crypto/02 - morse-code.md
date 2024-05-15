## Descripción
Morse code is well known. Can you decrypt this? Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

El código Morse es bien conocido. ¿Puedes descifrar esto? Descargue el archivo [aquí](https://artifacts.picoctf.net/c/79/morse_chal.wav). Envuelva su respuesta con picoCTF{}, coloque guiones bajos en lugar de pausas y use todo en minúsculas.
### Pistas
1. Audacity is a really good program to analyze morse code audio.

1. Audacity es un programa realmente bueno para analizar audio en código morse.
### Solución
```
1. Descargamos el audio del reto.
2. Vamos a International Morse Decoders(https://morsecode.world/international/decoder/)
3. Presionamos en "Upload" y seleccionamos nuestro audio descargado
4. Hacemos clic en "Play" y se nos da un mensaje mientras se escucha:
5. Se da WH47 H47H 90D W20U9H7, pero en los espacios hay que sustituirlos con guiones bajos("_")
6. La bandera resultante es: picoCTF{WH47_H47H_90D_W20U9H7}
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/280
***International Morse Decoders:*** https://morsecode.world/international/decoder/