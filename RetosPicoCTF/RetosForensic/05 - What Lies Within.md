## Descripcion
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

Hay algo en este [edificio](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). ¿Puedes recuperar la bandera?
### Pistas
1. There is data encoded somewhere... there might be an online decoder.

1. Hay datos codificados en alguna parte... puede que haya un decodificador en línea.
### Solución
```
1. Se necesita que convertir la imagen descargada.
2. Vamos a Steganography Online (Link abajo).
3. En este decodificador de imagenes se puede obtener diferentes mensajes de diferentes imagenes ocultos por la esteganografía.
4. Cambiamos a la pestaña de "Decode"
5. Cargamos la imagen y presionamos "Decode"
6. Se nos mostrará la bandera en la salida.
```
### Notas Adicionales
En este reto aprendimos a como entender la esteganografía, la esteganografía (del griego στεγανος steganos, "cubierto" u "oculto", y γραφος graphos, "escritura") trata el estudio y aplicación de técnicas que permiten ocultar mensajes u objetos, dentro de otros, llamados portadores, para que no se perciba su existencia.
### Referencias
https://play.picoctf.org/practice/challenge/74
***Esteganografía en línea:*** https://stylesuxx.github.io/steganography/