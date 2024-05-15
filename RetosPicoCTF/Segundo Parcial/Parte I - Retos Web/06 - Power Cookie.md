## Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:63041/) and see what you can discover.

¿Puedes conseguir la bandera? Ve a este [sitio web](http://saturn.picoctf.net:63041/) y mira lo que puedes descubrir.
### Pistas
1. Do you know how to modify cookies?

1. ¿Sabes cómo modificar las cookies?
### Solución
```
1. Accedemos al sitio web y podemos ver que se tiene un botón sencillo.
2. Al hacer clic se nos manda a una página que dice que no hay servicios disponibles.
3. Necesitamos un editor de cookies como Cookie Editor.
4. Al ver las cookies que se manejan se puede ver que simplemente tenemos una cookie llamada "isAdmin" (traducida al español como "esAdministrador") con valor de 0. Que por lo general es un false en datos booleanos.
5. Cambiamos el valor de esta cookie a 1 y la guardamos.
6. La bandera es: picoCTF{gr4d3_A_c00k13_0d351e23}
```
### Notas Adicionales
Las cookies son **archivos de datos (no códigos) creados y enviados por un sitio web y almacenados en el navegador del usuario**. De esta forma, el sitio web puede consultar la actividad previa del navegador y detectar las páginas visitadas por el usuario.
### Referencias
https://play.picoctf.org/practice/challenge/288