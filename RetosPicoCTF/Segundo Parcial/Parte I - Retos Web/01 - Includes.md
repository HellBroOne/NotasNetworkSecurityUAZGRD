## Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:50761/) and see what you can discover.

¿Puedes conseguir la bandera? Ve a este [sitio web](http://saturn.picoctf.net:50761/) y ve lo que puedes descubrir.
### Pistas
1. Is there more code than what the inspector initially shows?

1. ¿Hay más código del que muestra inicialmente el inspector?
### Solución
```
1. Abrimos el sitio, hacemos clic derecho y hacemos clic en dónde dice "Inspeccionar"
2. En el inspaector nos vamos a la parte de "Sources" o "Recursos"
3. La segunda parte de la bandera se encuentra en el archivo CSS de la página. Con picoCTF{1nclu51v17y_1of2_
4. La tercera parte de la bandera está en el código javascript de la página. Siendo f7w_2of2_df589022}
5. Entonces la bandera es: picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}
```
### Notas Adicionales
El inspector de archivos nos permite obtener el código de la hoja de estilos de la página así como el código de javascript.
A veces a los "include" se les llama "copy" o "import".
### Referencias
https://play.picoctf.org/practice/challenge/274