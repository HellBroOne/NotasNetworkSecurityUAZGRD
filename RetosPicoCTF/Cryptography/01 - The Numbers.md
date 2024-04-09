## Descripcion
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

Los [números](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... ¿qué significan?
### Pistas
1. The flag is in the format PICOCTF{}

1. La bandera tiene el formato PICOCTF{}
### Solución
```
1. Descargamos la imagen de pico
2. La bandera dice: 16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }
3. Podemos ver que si es picoCTF al principio, cada letra entonces esta equivalente a su numero en el alfabeto.
4. En cyberchef desencriptamos de A1Z26 Cipher Decode que es cada letra con su numero actual.
5. La bandera es: picoctf{thenumbersmason}
```
### Notas Adicionales
**A1Z26** **es** un cifrado por sustitución directa muy simple, donde cada letra del alfabeto se reemplaza por su número en el alfabeto.
### Referencias
https://play.picoctf.org/practice/challenge/68
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)