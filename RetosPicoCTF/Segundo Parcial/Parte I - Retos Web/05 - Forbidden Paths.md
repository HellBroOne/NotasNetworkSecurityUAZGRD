## Descripcion
Can you get the flag?Here's the [website](http://saturn.picoctf.net:58179/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

¿Puedes obtener la bandera? Aquí está el [sitio web](http://saturn.picoctf.net:58179/). Sabemos que los archivos del sitio web se encuentran en `/usr/share/nginx/html/` y la bandera está en `/flag.txt` pero el sitio web filtra rutas absolutas de archivos. ¿Puedes pasar el filtro para leer la bandera?
### Pistas
(None)

(Ninguna)
### Solución
```
1. Abrimos el sitio de la descripcion.
2. Vemos que si escribimos el '/usr/share/nginx/html/flag.txt' no funciona, no estamos autorizados.
3. Para ello, hay que usar rutas relativas que constan de una ruta descrita desde un punto de inicio.
4. Escribimos '../../../../flag.txt' y se nos demuestra que haciendo uso del directorio anterior se nos da la bandera.
5. La bandera es: picoCTF{7h3_p47h_70_5ucc355_6db46514}
```
### Notas Adicionales
Las rutas relativas: **son indicadas a partir de donde este en ese momento situado**. No se incluye el directorio raíz.
Las rutas absolutas: es **aquella en la que se indican todos los directorios de la jerarquía desde la raíz hasta el archivo o directorio final**.
### Referencias
https://play.picoctf.org/practice/challenge/270