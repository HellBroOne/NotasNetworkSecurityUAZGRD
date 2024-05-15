## Descripción
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/111/enc_flag).

¿Puedes entender el significado real de este archivo? Descarga el archivo [aquí](https://artifacts.picoctf.net/c_titan/111/enc_flag).
### Pistas
1. Engaging in various decoding processes is of utmost importance
1. Participar en varios procesos de decodificación es de suma importancia.
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/111/enc_flag
--2024-03-14 03:08:32--  https://artifacts.picoctf.net/c_titan/111/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                                       100%[===================================================================================================>]      73  --.-KB/s    in 0s      

2024-03-14 03:08:32 (5.11 MB/s) - 'enc_flag' saved [73/73]

hellbroone-picoctf@webshell:~$ file enc_flag
enc_flag: ASCII text
hellbroone-picoctf@webshell:~$ cat enc_flag
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==
hellbroone-picoctf@webshell:~$ ^C
hellbroone-picoctf@webshell:~$ echo "zacatecas" | base64
emFjYXRlY2FzCg==
hellbroone-picoctf@webshell:~$ base64 -d enc_flag
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ=='
hellbroone-picoctf@webshell:~$ echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ=="
| base64 -d
jcwiWNZ{wuymul_x3wl9jn3x_890x2379}
hellbroone-picoctf@webshell:~$ echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ==" | base64 -d | tr 'A-Za-z' 'T-ZA-St-za-s'
picoCTF{caesar_d3cr9pt3d_890d2379}
```

Otra solución pudo haber sido con Cyberchef, y decodificar así:
1. De Base64 (y quedarnos con lo que esta dentro del b'')
2. Volver a decodificar De Base64
3. Usar ROT13 con valor de 19.
### Notas Adicionales
Para este reto simplemente hay que hacer decodificaciones y se usaron varios métodos de decodificación, siendo dos de base 64 pero para el segundo hay que eliminar los caracteres de la "b" y los dos apostrofes a los que encierra. Luego volver a decodificar a Base64 y por ultimo a un ROT19. Este reto nos ayuda a poder comprender varias partes de cadenas Encriptadas en varios lenguajes de encriptación y poder comprender la criptografía.

### Referencias
***Decodificador CyberChef:*** https://gchq.github.io/CyberChef/
***Reto:*** https://play.picoctf.org/events/73/challenges/challenge/418
