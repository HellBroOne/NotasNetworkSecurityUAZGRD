## Descripcion
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:59901/) out.

La bandera está en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntralo. Mira [esto](http://saturn.picoctf.net:59901/).
### Pistas
(None)

(Ninguna)
### Solución
```
1. Accedemos al sitio web y podemos ver que se tiene un botón sencillo.
2. Al hacer clic se nos manda a una página (de yoga o yo que se xd), entonces no tenemos nada en concreto.
4. Sin embargo, tenemos una página que nos ayuda a rastrear el tráfico de una página llamada "robots.txt". Escribimos en el final de la url de la página "/robots.txt"
5. Accedemos y se nos da lo siguiente:
6.  User-agent *
	Disallow: /cgi-bin/
	Think you have seen your flag or want to keep looking.

	ZmxhZzEudHh0;anMvbXlmaW
	anMvbXlmaWxlLnR4dA==
	svssshjweuiwl;oiho.bsvdaslejg
	Disallow: /wp-admin/
7. Se puede observar que tenemos una parte de disallow y básicamente en disallow siempre está el sitio que no está habilitado para la navegación.
8. Al ver esta parte tenemos 3 cadenas de texto codificadas en diferentes encodificaciones. Si ponemos la primera y la tercera no se nos dará nada en especifico, pero al decodificar de Base64 la segunda cadena nos dará como resultado: js/myfile.txt
9. Esto es una ruta específica a dónde podemos ir (ya que al escribir al final de la URL "/wp-admin/" no nos lleva a ninguna página), entonces si escribimos "/js/myfile.txt" en vez de "/robots.txt" nos llevará a la página de la bandera.
10. La bandera es: picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```
### Notas Adicionales
El archivo *robots.txt* está en cualquier página, y sirve para gestionar el tráfico de rastreadores en una página.
### Referencias
https://play.picoctf.org/practice/challenge/291