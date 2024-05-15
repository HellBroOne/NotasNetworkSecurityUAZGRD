## Descripción
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:60616/) to find the flag

¿Sabes cómo utilizar el inspector web? Empieza a buscar [aquí](http://titan.picoctf.net:60616/) para encontrar la bandera.
### Pistas
1. Use the web inspector on other files included by the web page.
2. The flag may or may not be encoded.
1. Utilice el inspector web en otros archivos incluidos en la página web.
2. La bandera puede estar codificada o no.
### Solución
```
1. Vamos primero a la pagina del reto.
2. Se nos dan tres paginas para inspeccionarlas, a partir de un rato, vemos que la pagina de "About" es la indicada.
3. Al inspeccionarla hay una variable que es la siguiente: notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZjZmNmI3OGF9"
4. Esta posiblemente es la bandera, para ello lo que hice fue tomar la cadena que se nos proporciona y vamos a CyberChef.
5. Buscando despues de un rato, podemos ver que esta bandera esta codificada en Base64
6. Al decodificarla, obtenemos: picoCTF{web_succ3ssfully_d3c0ded_f6f6b78a}
```

### Notas Adicionales
Para este reto simplemente hay que saber usar el inspector web de todos los navegadores y gracias a ello, también pudimos encontrar la parte de la bandera pero sabiendo diferentes partes de la decodificación, podemos hacer uso de Base64 para hacerlo.

### Referencias
***Decodificador CyberChef:*** https://gchq.github.io/CyberChef/
***Reto:*** https://play.picoctf.org/events/73/challenges/challenge/427
***Página del Reto:*** http://titan.picoctf.net:60616/about.html
