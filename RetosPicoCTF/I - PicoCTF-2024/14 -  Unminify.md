## Objetivo
I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster! Browse [here](http://titan.picoctf.net:59471/), and find the flag!

No me gusta desplazarme hacia abajo para leer el código de mi sitio web, así que lo he aplastado. Además, mis páginas se cargan más rápido.  
Navega aquí y encuentra la bandera.
## Pistas
1. Try CTRL+U / ⌘+U in your browser to view the page source. You can also add 'view-source:' before the URL, or try `curl <URL>` in your shell.
	1. Prueba CTRL+U / ⌘+U en tu navegador para ver la fuente de la página. También puedes añadir 'view-source:' antes de la URL, o probar curl \<URL> en tu shell.
2. Minification reduces the size of code, but does not change its functionality.
	2. La minificación reduce el tamaño del código, pero no cambia su funcionalidad.
3. What tools do developers use when working on a website? Many text editors and browsers include formatting.
	3. ¿Qué herramientas utilizan los programadores cuando trabajan en un sitio web? Muchos editores de texto y navegadores incluyen formateo.
## Solución
1. Ingresamos a la página correspondiente al reto.
2. Inspeccionamos el código fuente de la página.
3. Vemos que el código está minificado, lo que dificulta su lectura. Por lo tanto, copiamos ese código.
4. Al estar minificado, hay que desminificarlo, por lo que nos tenemos que apoyar de una página que haga esto.
5. Una vez hecho lo anterior, ahora sí podemos leer el código con mayor facilidad, lo que nos permite visualizar en una parte de este la bandera.

*Bandera del reto: picoCTF{pr3tty_c0d3_dbe259ce}*
## Notas adicionales

## Referencias
* Herramienta para desminificar código: [Desminificar HTML: Mejorar la legibilidad y el proceso de desarrollo (nero.com)](https://www.nero.com/eng/webservices/nero-unminifyhtml/?currency=eur&vlang=mx) 
* Minificación: [¿Qué es la minificación y por qué hacerla? | BHOOST.COM](https://www.bhoost.com/es/que-es-la-minificacion-y-por-que-hacerla/) 