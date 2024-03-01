## Descripcion
What is 0x3D (base 16) in decimal (base 10)?

¿Qué es 0x3D (base 16) en decimal (base 10)?
### Pistas
1. Submit your answer in our flag format. For example, if your answer was '22', you would submit 'picoCTF{22}' as the flag.
### Solución
```
1. Para esto primero hay que obtener el 0x3D.
2. Para decodificar, use "Cyberchef"
3. Primero agregamos "From Base" a la receta.
4. Hay que especificar que vamos a convertir de Base16 en "Radix"
5. Pegamos el 0x3D y resulta un 61
6. La respuesta es picoCTF{61}
```
### Notas Adicionales
Aquí aprendimos a decodificar desde métodos externos un archivo de base 16 a base 10, utilizando CyberChef y su decodificador de Base usando el radix 16.
### Referencias
https://play.picoctf.org/practice/challenge/58
*Decodificador de CyberChef:* [Cyberchef](https://gchq.github.io/CyberChef/)