## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!

Dejé de usar YellowPages y pasé a WhitePages... pero [la página que me dieron](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) ¡está toda en blanco!
### Pistas
(None)

(Ninguna)
### Solución
```
hellbroone-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
--2024-03-19 18:33:34--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2964 (2.9K) [application/octet-stream]
Saving to: 'whitepages.txt'

whitepages.txt                                 100%[===================================================================================================>]   2.89K  --.-KB/s    in 0s      

2024-03-19 18:33:34 (997 MB/s) - 'whitepages.txt' saved [2964/2964]

hellbroone-picoctf@webshell:~$ xxd -g 1 -l 100 whitepages.txt
00000000: e2 80 83 e2 80 83 e2 80 83 e2 80 83 20 e2 80 83  ............ ...
00000010: 20 e2 80 83 e2 80 83 e2 80 83 e2 80 83 e2 80 83   ...............
00000020: 20 e2 80 83 e2 80 83 20 e2 80 83 e2 80 83 e2 80   ...... ........
00000030: 83 e2 80 83 20 e2 80 83 e2 80 83 20 e2 80 83 20  .... ...... ... 
00000040: 20 20 e2 80 83 e2 80 83 e2 80 83 e2 80 83 e2 80    ..............
00000050: 83 20 20 e2 80 83 20 e2 80 83 e2 80 83 20 e2 80  .  ... ...... ..
00000060: 83 20 20 e2
hellbroone-picoctf@webshell:~$ cat whitepages.txt
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              hellbroone-picoctf@webshell:~$ :v
-bash: :v: command not found
hellbroone-picoctf@webshell:~$ sed 's/\xe2\x80\x83/0/g' whitepages.txt | sed 's/\x20/1/g'
00001010000010010000100101110000011010010110001101101111010000110101010001000110000010100000101000001001000010010101001101000101010001010010000001010000010101010100001001001100010010010100001100100000010100100100010101000011010011110101001001000100010100110010000000100110001000000100001001000001010000110100101101000111010100100100111101010101010011100100010000100000010100100100010101010000010011110101001001010100000010100000100100001001001101010011000000110000001100000010000001000110011011110111001001100010011001010111001100100000010000010111011001100101001011000010000001010000011010010111010001110100011100110110001001110101011100100110011101101000001011000010000001010000010000010010000000110001001101010011001000110001001100110000101000001001000010010111000001101001011000110110111101000011010101000100011001111011011011100110111101110100010111110110000101101100011011000101111101110011011100000110000101100011011001010111001101011111011000010111001001100101010111110110001101110010011001010110000101110100011001010110010001011111011001010111000101110101011000010110110001011111011000110011010100110100011001100011001000110111011000110110010000110000001101010110001100110010001100010011100000111001011001100011100000110001001101000011011101100011011000110011011001100110001101010110010001100101011000100011001001100101001101010011011001111101000010100000100100001001
hellbroone-picoctf@webshell:~$      

[EN CYBERCHEF]
1. Se necesita que convertir la cadena binaria.
2. Vamos a Cyberchef
3. Elegimos la opcion de "From Binary" y decodificara
4. Nos dara la bandera: picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
```
### Notas Adicionales
En este reto aprendimos que no todos los espacios son del mismo tipo de carácter y que el código ASCII contiene varios tipos de espacios en blanco.
### Referencias
https://play.picoctf.org/practice/challenge/51
***Decodificador de CyberChef:*** [Cyberchef](https://gchq.github.io/CyberChef/)