## Descripción
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Ahora NO me ves. Este [informe](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) contiene algunos datos críticos, algunos de los cuales han sido redactados correctamente, mientras que otros no... ¿Puedes encontrar una clave importante que no haya sido redactada correctamente?
### Pistas
1. How can you be sure of the redaction?

1. ¿Cómo puedes estar segur@ de la redacción?
### Solución
```
Creo que hay dos maneras de solucionar este reto, la mas sencilla es la siguiente:
1. Descargamos el archivo y con cualquier lector de PDF lo abrimos.
2. Con control+f podemos buscar en un archivo, nosotros buscamos escribiendo "pico"
3. Se nos muestra que en una parte de un cuadro negro no se ve pero ahí está la bandera.
4. La seleccionamos y esta es: picoCTF{C4n_Y0u_S33_m3_fully}

Hay otra forma que necesita el uso de Word:
1. Descargamos el archivo y con Word lo abrimos.
2. Podemos cambiar el color de la tipografía a otro color que no sea negro y se nos revelan los textos ocultos.
3. La bandera está al final del archivo: picoCTF{C4n_Y0u_S33_m3_fully}
```
### Notas Adicionales
Control + f (o Find o Buscar) en algunos visualizadores de texto funcionan para poder obtener una cadena de texto que necesitemos en algún archivo.
A veces word nos puede ayudar a abrir archivos PDF.
### Referencias
https://play.picoctf.org/practice/challenge/290