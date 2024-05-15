## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

En RSA, un valor "e" pequeño puede ser problemático, pero ¿qué pasa con "N"? ¿Puedes descifrar esto? [valores](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)
### Pistas
1. Bits are expensive, I used only a little bit over 100 to save money

1. Los bits son caros, usé solo un poco más de 100 para ahorrar dinero
### Solución
```
1. Descargamos el archivo y lo abrimos con cat, este dira lo siguiente:
2. Vamos a factordb (http://factordb.com/) y ponemos "n" en la caja de texto para poder proceder a factorizar.
3. Uno de los dos numeros es p y otro es q (no importa cual elijamos para cada uno).
4. Vamos a python para desencriptar:
Python 3.12.0 (tags/v3.12.0:0fb18b0, Oct  2 2023, 13:03:39) [MSC v.1935 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license()" for more information.
>>> p = 1461849912200000206276283741896701133693
>>> q = 431899300006243611356963607089521499045809
>>> n = p*q
>>> n
	631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> tn = (p - 1) * (q - 1)
>>> e = 65537
>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> d = pow(e, -1, tn)
>>> m = pow(c, d, n)
>>> bytes.fromhex( hex(m)[2:])
	b'picoCTF{sma11_N_n0_g0od_55304594}'
5. La bandera es: picoCTF{sma11_N_n0_g0od_55304594}
```
### Notas Adicionales
**El RSA (Rivest–Shamir–Adleman)** es un algoritmo utilizado por las computadoras modernas para cifrar y descifrar mensajes. Es un algoritmo criptográfico asimétrico. Asimétrico significa que hay dos claves diferentes.
Criptografía de Llave pública.
Nomenclatura:
***m =*** texto plano
***c =*** texto cifrado
***p =*** número primo
***q =*** número primo
***n =*** módulo
***e =*** llave pública (n^16+1 = )
***tn =*** totient (euler)
***d =*** llave privada

Fórmulas:
***n =*** p * q
***tn =*** (p - 1) * (q - 1)
***d =*** e mod inu tn -- pow(e, -1, tn)
***c =*** m ^ e mod n -- pow(m, e, n)
***m =*** c^d mod n -- pow(e, d, n)
### Referencias
https://play.picoctf.org/practice/challenge/162
***Factorizar n, FactorDB:*** http://factordb.com/