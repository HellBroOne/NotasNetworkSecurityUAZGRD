## Descripcion
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 21610`.

Hay golpecitos provenientes de los cables. ¿Qué dice `nc jupiter.challenges.picoctf.org 21610`?
### Pistas
1. What kind of encoding uses dashes and dots?
2. The flag is in the format PICOCTF{}

1. ¿Qué tipo de codificación utiliza guiones y puntos?
2. La bandera tiene el formato PICOCTF{}
### Solución
```
┌──(loro㉿KaliLinux)-[~/tapping]
└─$ nc jupiter.challenges.picoctf.org 21610
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ...-- ----. ----- ..--- ----- .---- ----. ..... .---- ----. }

Vamos a Cyberchef para decodificar
1. Como esto suena a Codigo Morse, podemos convertir "From Morse"
2. Pegamos el texto de guiones y puntos.
3. La bandera es PICOCTF{M0RS3C0D31SFUN3902019519}
```
### Notas Adicionales
El código morse, también conocido como alfabeto morse o clave morse es un sistema de representación de letras y números mediante señales emitidas de forma intermitente.
### Referencias
https://play.picoctf.org/practice/challenge/21
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)