## Objetivo
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 64026`

## Pistas

## Solución
```
┌──(kali㉿kali)-[~/picoctf/concurso/binhexa]
└─$ nc titan.picoctf.net 64026

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00011000
Binary Number 2: 11110101


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100001101
Correct!

Question 2/6:
Operation 2: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1011011111000
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111101
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 00110000
Correct!

Question 5/6:
Operation 5: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00010000
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01111010
Correct!

Enter the results of the last operation in hexadecimal: 7A

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_1367e2c6}
                                                                                                                                                                                                                   
┌──(kali㉿kali)-[~/picoctf/concurso/binhexa]
└─$ 

```
## Notas Adicionales
">>" : es recorrer el numero binario 2 un digito hacia la derecha. Si era  11110101 se pone un cero a la izquierda y asi los demas numeros se recorren un bit 01111010
"<<" : es recorrer el numero binario 1 un digito hacia la izquierda. Si era  00011000 se pone un cero a la derecha y asi los demas numeros se recorren un bit 00110000
"&" :  cada bit en la misma posición en ambos números se compara, y el resultado será 1 en esa posición solo si ambos bits son 1, de lo contrario, será 0.
" | " : cada bit en la misma posición en ambos números se compara, y si al menos uno de los bits es 1, el resultado será 1 en esa posición, de lo contrario, será 0.

## Referencias
https://gchq.github.io/CyberChef/
