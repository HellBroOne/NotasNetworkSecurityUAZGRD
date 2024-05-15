## Descripción
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 49700`

¡Nuestro servicio de impresión de banderas ha comenzado a fallar!`$ nc saturn.picoctf.net 49700`
### Pistas
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
### Solución
```
hellbroone-picoctf@webshell:~$ nc saturn.picoctf.net 49700
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
^C
hellbroone-picoctf@webshell:~$ python   
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
KeyboardInterrupt
>>> chr(0x61)
'a'
>>> chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65)
'a4392d2e'
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}')
picoCTF{gl17ch_m3_n07_a4392d2e}
>>> exit()
hellbroone-picoctf@webshell:~$ exit
logout

Webshell session has ended.
```
### Notas Adicionales
Para este nivel usamos python y sus métodos de chr(), los cuáles obtienen el valor de un caracter y lo decodifican a ASCII para posteriormente pasarlos a una cadena completa. Esto lo obtuvimos mediante una conexión de netcat dónde pudimos conectarnos al servidor mencionado y por un puerto, así fue como nos dieron la cadena de python la cuál simplemente era imprimirla.
### Referencias
https://play.picoctf.org/practice/challenge/242