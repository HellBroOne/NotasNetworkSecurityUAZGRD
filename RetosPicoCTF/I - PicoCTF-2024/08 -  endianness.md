## Descripción
Know of little and big endian? Additional details will be available after launching your challenge instance. `nc titan.picoctf.net 49656`. [Source](https://artifacts.picoctf.net/c_titan/78/flag.c)

¿Conoces el little y el big endian? Detalles adicionales estarán disponibles después de lanzar su instancia de desafío. `nc titan.picoctf.net 49656`. [Fuente](https://artifacts.picoctf.net/c_titan/78/flag.c)
### Pistas
1. You might want to check the ASCII table to first find the hexadecimal representation of characters before finding the endianness.
2. Read more about how endianness [here](https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7)

1. Es posible que desee consultar la tabla ASCII para encontrar primero la representación hexadecimal de los caracteres antes de encontrar el endianismo.
2. Lea más sobre cómo funciona el endianismo [aquí](https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7)
### Solución
Para saber un poco de las Big y Little Endians hay que mantener una tabla ASCII para poder comprender como se representan los caracteres en formatos hexadecimales, una vez con esta tabla hay que unir las palabras para poder comprender cual es la big y little endian.
```
hellbroone-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/78/flag.c
--2024-03-14 04:24:15--  https://artifacts.picoctf.net/c_titan/78/flag.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3666 (3.6K) [application/octet-stream]
Saving to: 'flag.c'

flag.c                                         100%[===================================================================================================>]   3.58K  --.-KB/s    in 0s      

2024-03-14 04:24:15 (33.7 MB/s) - 'flag.c' saved [3666/3666]

hellbroone-picoctf@webshell:~$ nano flag.c
hellbroone-picoctf@webshell:~$ nc titan.picoctf.net 60949
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: ohixy
Enter the Little Endian representation: 797869686F
Correct Little Endian representation!
Enter the Big Endian representation: 6F68697879
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_cfe38ef0}

^C
hellbroone-picoctf@webshell:~$ 
```

### Notas Adicionales
Para este reto aprendimos que son las little y big endian que se definen sobre el concepto de la endianidad, siendo el término inglés endianness (y en español extremidad o a veces endianidad) designa el formato en el que se almacenan los datos de más de un byte en un ordenador. El problema es similar a los idiomas en los que se escriben de derecha a izquierda, como el árabe, o el hebreo, frente a los valores de bits.

### Referencias
***Little Endian and Big Endian:*** https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7
***Reto:*** https://play.picoctf.org/events/73/challenges/challenge/414
