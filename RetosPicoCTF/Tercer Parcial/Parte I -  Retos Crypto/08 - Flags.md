## Descripción
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

¿Qué significan las [banderas](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png)?
### Pistas
1. The flag is in the format PICOCTF{}

1. La bandera tiene el formato PICOCTF{}
### Solución
```
1. Descargamos la imagen del archivo.
2. Se nos muestra lo siguiente:
```
![[Pasted image 20240514132709.png]]
```
3. Se puede deducir que son las banderas de varios paises o menciones, entonces lo que pienso hacer es obtener la primera letra del pais que representan
4. Investigando un poco, estas banderas hacen referencia al codigo de señales de banderas, como el siguiente:
```
![[Pasted image 20240514133428.png]]
```
5. Haciendo las substituciones, se tienen las banderas de esta manera:
	numeros de banderas: [1 2 3 4 5 6 7 { 8 9 10 11 12 13 14 15 16 17 18 19 20}]
	mensaje:             [P I C O C T F { F 1  A  G  5  A  N  D  5  T  U  F  F}] 
6. La bandera es la siguiente: PICOCTF{F1AG5AND5TUFF}
```
### Notas Adicionales
Cabe decir que algunas de las banderas son alternativas a otras como la amarilla con una "X" azul (bandera 12 y 16) es bandera alternativa a la del  cinco, y la de los colores Rojo en los extremos y amarillo en medio (la bandera 9) es alternativa al 1.
Para encontrarlas banderas también se puede usar un identificador de banderas, como el de la segunda referencia.
### Referencias
https://play.picoctf.org/practice/challenge/31
***FlagID:*** https://flagid.org/flagid_combined.asp