## Descripcion
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

¿Qué significa esto `bDNhcm5fdGgzX3IwcDM1` ? Creo que tiene algo que ver con las bases.
### Pistas
1. Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.
### Solución
```
1. Para esto primero hay que obtener la cadena de bDNhcm5fdGgzX3IwcDM1.
2. Para decodificar, use "Cyberchef"
3. Agregamos la base64 a la receta.
4. Nos resulta en "l3arn_th3_r0p35"
5. La respuesta es picoCTF{l3arn_th3_r0p35}
```
### Notas Adicionales
Aquí aprendimos a decodificar desde métodos externos un texto de base64 a base 10, utilizando CyberChef y su decodificador de From Base64.
### Referencias
https://play.picoctf.org/practice/challenge/67
*Decodificador de CyberChef:* [Cyberchef](https://gchq.github.io/CyberChef/)