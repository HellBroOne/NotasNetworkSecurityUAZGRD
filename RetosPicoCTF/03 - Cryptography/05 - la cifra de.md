## Descripción
I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 32411`.

Encontré este cifrado en un libro antiguo. ¿Puedes entender lo que dice? Conéctate con `nc jupiter.challenges.picoctf.org 32411`.
### Pistas
1. There are tools that make this easy.
2. Perhaps looking at history will help.

1. Existen herramientas que lo hacen fácil.
2. Quizás sea útil mirar la historia.
### Solución
```
┌──(loro㉿KaliLinux)-[~/lacifrade]
└─$ nc jupiter.challenges.picoctf.org 32411
Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3x7g996649}

Ehk ktryy herq-ooizxetypd jjdcxnatoty ol f aordllvmlbkytc inahkw socjgex, bls sfoe gwzuti 1467 my Rjzn Hfetoxea Gqmexyt.

Tnj Gimjyèrk Htpnjc iy ysexjqoxj dosjeisjd cgqwej yse Gqmexyt Doxn ox Fwbkwei Inahkw.

Tn 1508, Ptsatsps Zwttnjxiax tnbjytki ehk xz-cgqwej ylbaql rkhea (g rltxni ol xsilypd gqahggpty) ysaz bzuri wazjc bk f nroytcgq nosuznkse ol yse Bnretèwp Cousex.

Para este texto vamos a Vigenere Solver.
1. Pegamos el texto en Viginere Solver
2. Hacemos clic en "Break Cipher" y se nos dice que la llave era "flag"
3. Con esa llave, podemos obtener la bandera: picoCTF{b311a50_0r_v1gn3r3_c1ph3r7b996649}
```
### Notas Adicionales
El cifrado de Vigenère es un cifrado basado en diferentes series de caracteres o letras del cifrado César formando estos caracteres una tabla, llamada tabla de Vigenère, que se usa como clave. El cifrado de Vigenère es un cifrado por sustitución simple polialfabético.
### Referencias
**Viginere Solver:** https://www.guballa.de/vigenere-solver
https://play.picoctf.org/practice/challenge/3