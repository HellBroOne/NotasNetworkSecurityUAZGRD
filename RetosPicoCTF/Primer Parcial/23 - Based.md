## Descripción
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

Para obtener realmente 1337, debes comprender diferentes codificaciones de datos, como hexadecimal o binaria. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conéctese con `nc jupiter.challenges.picoctf.org 29221`.
### Pistas
1. I hear python can convert things.
2. It might help to have multiple windows open.
### Solución
1. Para este programa tuve a la par a CyberChef para decodificar de varios métodos de encriptación
2. Primero se tiene que encriptar una palabra de binario a texto.
3. Luego es una palabra de Octal a texto.
4. Finalmente, es una palabra de Hexadecimal a texto.
5. Todo esto en 45 segundos, y las palabras cambian en cada vez que ejecutemos el servidor.
Mi solución fue esta:
```
hellbroone-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
chair
Please give the 01100011 01101000 01100001 01101001 01110010 as a word.
...
you have 45 seconds.....

Input:
chair
Please give me the  160 151 145 as a word.
Input:
pie
Please give me the 706965 as a word.
Input:
pie
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
^C
hellbroone-picoctf@webshell:~$ exit 
logout

Webshell session has ended.
```
### Notas Adicionales
Aquí aprendimos a decodificar desde métodos externos una cadena, primero a Binaria, luego a convertirla de Octal a base decimal, para último de Hexadecimal a base 10 para poder obtener la bandera, usando CyberChef.
### Referencias
https://play.picoctf.org/practice/challenge/35
*Decodificador de CyberChef:* [Cyberchef](https://gchq.github.io/CyberChef/)