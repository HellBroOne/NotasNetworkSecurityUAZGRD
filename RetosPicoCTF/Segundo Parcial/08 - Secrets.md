## Descripcion
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:65455/).

Tenemos varias páginas ocultas. ¿Puedes encontrar la que tiene la bandera? El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:65455/).
### Pistas
1. folders folders folders

1. carpetas carpetas carpetas
### Solución
```
1. Accedemos al sitio web y no hay nada más que tres páginas diferentes.
2. La pista indica que son carpetas tras carpetas, por ende hay que verificar los recursos en la pestaña de "Resources".
3. Hay una imagen que está en una carpeta muy originalmente llamada "secret"
4. Si accedemos escribiendo "/secret/" al final de la URL actual nos lleva a una página que dice: "Finally. You almost found me. you are doing well (Finalmente. Casi me encuentras. lo estás haciendo bien)", entonces vamos bien.
5. Checando de nuevo los recursos nos podemos dar cuenta que el código de la página actual está en la misma carpeta dónde hay otra llamada "hidden"
6. Si accedemos escribiendo "/hidden/" al final de la nueva URL actual nos lleva a una página que parece un Login, pero no se confundan panas, esta página simplemente es una trampa para no continuar.
7. Checando otra vez los recursos nos podemos dar cuenta que el código de la página actual está en la misma carpeta dónde hay otra llamada "superhidden"
8. Si accedemos escribiendo "/superhidden/" al final de la nueva URL actual nos lleva a una página que dice: "Finally. You found me. But can you see me (Finalmente. Me encontraste. ¿Pero puedes verme?)".
9. Lo gracioso es que la bandera está escrita en letra blanca, simplemente con seleccionar todo el texto de la página o con cambiar las letras de la flag en el CSS a negro se nos revela.
10. La bandera es: picoCTF{succ3ss_@h3n1c@10n_39849bcf}
```
### Notas Adicionales
En el inspector de páginas siempre se nos puede hacer una consulta de algunos archivos que usa la página actual que esta mostrandose, siempre y cuando los use esa página estos se mostraran fácilmente.
### Referencias
https://play.picoctf.org/practice/challenge/296