## Descripción
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://artifacts.picoctf.net/c/181/message.txt).

Ha llegado un segundo mensaje por correo y parece casi idéntico al primero. Quizás vuelva a funcionar lo mismo. Descargue el mensaje [aquí](https://artifacts.picoctf.net/c/181/message.txt).
### Pistas
1. Try a frequency attack.
2. Do the punctuation and the individual words help you make any substitutions?

1. Pruebe un ataque de frecuencia.
2. ¿La puntuación y las palabras individuales te ayudan a realizar alguna sustitución?
### Solución
```
1. Descargamos el archivo txt del reto.
2. Al hacer un "cat" se muestra que el texto contiene lo siguiente:
ZWDg (gejfw djf zacwpfx wex dqar) afx a wscx jd zjicpwxf gxzpfbws zjicxwbwbjv. Zjvwxgwavwg afx cfxgxvwxm hbwe a gxw jd zeaqqxvrxg hebze wxgw wexbf zfxawbybws, wxzevbzaq (avm rjjrqbvr) gnbqqg, avm cfjtqxi-gjqybvr atbqbws. Zeaqqxvrxg pgpaqqs zjyxf a vpitxf jd zawxrjfbxg, avm hexv gjqyxm, xaze sbxqmg a gwfbvr (zaqqxm a dqar) hebze bg gptibwwxm wj av jvqbvx gzjfbvr gxfybzx. ZWDg afx a rfxaw has wj qxafv a hbmx affas jd zjicpwxf gxzpfbws gnbqqg bv a gadx, qxraq xvybfjvixvw, avm afx ejgwxm avm cqasxm ts iavs gxzpfbws rfjpcg afjpvm wex hjfqm djf dpv avm cfazwbzx. Djf webg cfjtqxi, wex dqar bg: cbzjZWD{DF3LP3VZS_4774ZN5_4F3_Z001_4871X6DT}
	
Dsu mxow vj: pvncNDM{5YH5717Y710G_3I0XY710G_03055505}

3. Para esto debemos hacer uso de una herramienta de ataque de frecuencia, en este caso utilizare la de "Mono-alphabetic Substitution"
4. Pegamos el texto en el cuadro de texto y hacemos clic en "Decrypt Automatically"
5. Se nos da el siguiente texto:
CTFS (SHORT FOR CAPTURE THE FLAG) ARE A TYPE OF COMPUTER SECURITY COMPETITION. CONTESTANTS ARE PRESENTED WITH A SET OF CHALLENGES WHICH TEST THEIR CREATIVITY, TECHNICAL (AND GOOGLING) SZILLS, AND PROBLEM-SOLVING ABILITY. CHALLENGES USUALLY COVER A NUMBER OF CATEGORIES, AND WHEN SOLVED, EACH YIELDS A STRING (CALLED A FLAG) WHICH IS SUBMITTED TO AN ONLINE SCORING SERVICE. CTFS ARE A GREAT WAY TO LEARN A WIDE ARRAY OF COMPUTER SECURITY SZILLS IN A SAFE, LEGAL ENVIRONMENT, AND ARE HOSTED AND PLAYED BY MANY SECURITY GROUPS AROUND THE WORLD FOR FUN AND PRACTICE. FOR THIS PROBLEM, THE FLAG IS: PICOCTF{FR3KU3NCY_4774CZ5_4R3_C001_4871E6FB}
6. Sustituimos en la bandera la "K" por "Q" y la "Z" por la "K".
7. La bandera al final es: picoCTF{FR3QU3NCY_4774CK5_4R3_C001_4871E6FB}
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/308
***Mono-alphabetic Substitution:*** https://www.dcode.fr/frequency-analysis