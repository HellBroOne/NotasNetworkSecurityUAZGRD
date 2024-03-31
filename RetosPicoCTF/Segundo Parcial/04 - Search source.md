## Descripcion
The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:63978/)

El desarrollador de este sitio web dejó por error un artefacto importante en la fuente del sitio web. ¿Puedes encontrarlo? El sitio web está [aquí](http://saturn.picoctf.net:63978/)
### Pistas
1. How could you mirror the website on your local machine so you could use more powerful tools for searching?

1. ¿Cómo podrías reflejar el sitio web en tu máquina local para poder utilizar herramientas de búsqueda más potentes?
### Solución
```
1. Abrimos la página y vemos el inspector de archivos.
2. Vamos a la pestaña source.
3. Presionamos ctrl+f (o cmd+f en MAC) para buscar una cadena en un archivo.
4. Escribimos "pico" para buscar la bandera en los archivos.
5. Esta bandera está en el archivo de style.css
6. La bandera es: picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49}
```
### Notas Adicionales
Control + f es de Find, que ayuda a encontrar una cadena en un archivo del código.
### Referencias
https://play.picoctf.org/practice/challenge/295