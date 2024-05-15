## Objetivo
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).
## Solución
```
Si abrimos el archivo como pdf nos da esta parte de la bandera:
1n_pn9_&_pdf_2a6a1ea8}
Pero cuando entramos a hexeditor vemos que realmente es un png por lo que cambiamos su extension y nos muestra una imagen con:
picoCTF{f1u3n7

Bandera:
picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}
```
## Notas adicionales
## Referencias