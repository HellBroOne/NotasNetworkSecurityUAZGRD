## Descripción
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

Si te dijera que una palabra comienza con 0x70 en hexadecimal, ¿con qué comenzaría en ASCII?
### Pistas
1. Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.
### Solución
```
1. Para esto primero hay que obtener el 0x70.
2. Para decodificar, use "Cyberchef"
3. Primero agregamos "From Hex" a la receta.
4. Pegamos el 0x70 y resulta una p
5. La respuesta es picoCTF{p}
```
### Notas Adicionales
Aquí aprendimos a decodificar desde métodos externos un archivo de Hexadecimal a ASCII, utilizando CyberChef y su decodificador de From Hex.
### Referencias
https://play.picoctf.org/practice/challenge/22
*Decodificador de CyberChef:* [Cyberchef](https://gchq.github.io/CyberChef/)