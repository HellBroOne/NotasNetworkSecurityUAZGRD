## Descripcion
There is some interesting information hidden around this site [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). Can you find it?

Hay información interesante oculta en este sitio [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). ¿Puedes encontrarlo?
### Pistas
1. You should have enough hints to find the files, don't run a brute forcer.

1. Deberías tener suficientes pistas para encontrar los archivos, no ejecutes fuerza bruta.
### Solución
```
1. La primera bandera esta oculta en el codigo fuente de la pagina: picoCTF{t
2. La segunda bandera esta en el CSS de la pagina: h4ts_4_l0
3. La tercera esta escribiendo robots.txt al final de la pagina (http://mercury.picoctf.net:55079/robots.txt): t_0f_pl4c
4. La cuarta esta en el .htaccess (http://mercury.picoctf.net:55079/.htaccess): 3s_2_lO0k
5. Finalmente, la ultima esta en el .DS_Store (http://mercury.picoctf.net:55079/.DS_Store): _74cceb07}

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}
```
### Notas Adicionales
Para este reto aprendimos obtener la bandera mediante el uso de varios indexes que se tienen el la url como tal, para ello fuimos partes por partes para obtener las banderas.
### Referencias
https://play.picoctf.org/practice/challenge/161
http://mercury.picoctf.net:55079/
