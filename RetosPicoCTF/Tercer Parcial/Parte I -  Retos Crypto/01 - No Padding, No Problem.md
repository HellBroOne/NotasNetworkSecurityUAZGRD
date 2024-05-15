## Descripción
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 10333`.

Los oráculos pueden ser tu mejor amigo, descifrarán cualquier cosa, excepto el texto cifrado de la bandera. ¿Cómo lo romperás? Conéctese con `nc mercury.picoctf.net 10333`.
### Pistas
1. What can you do with a different pair of ciphertext and plaintext? What if it is not so different after all...

1. ¿Qué se puede hacer con un par diferente de texto cifrado y texto sin formato? ¿Y si después de todo no es tan diferente...?
### Solución
```
┌──(loro㉿KaliLinux)-[~/nopad-noprob]
└─$ nc mercury.picoctf.net 10333
Welcome to the Padding Oracle Challenge
This oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Good Luck!


n: 74136135770312872344511684221813791169007737352744096583168417821002946076328922243166916875362169718489179608328112263106119026325847556823602463663364679295987727317453390631565762670309986346784805508962074855262722076322142613106156303442698040133198598346768569185219846573639493112509379985224555464917
e: 65537
ciphertext: 53461806473004828114691998577517605985469614676534560722682128519548059607242131145459345643829081870137366358065201975536740139222178039532706368808593953632178653123172070402222079021359151805045713072521026099563740712836548024937428227610387444705588172255783338863954001941863050266165728972689155475000


Give me ciphertext to decrypt: 53461806473004828114691998577517605985469614676534560722682128519548059607242131145459345643829081870137366358065201975536740139222178039532706368808593953632178653123172070402222079021359151805045713072521026099563740712836548024937428227610387444705588172255783338863954001941863050266165728972689155475000
Will not decrypt the ciphertext. Try Again
Give me ciphertext to decrypt: ^C
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/nopad-noprob]
└─$ nano exploiter.py       
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/nopad-noprob]
└─$ cat exploiter.py 
#importamos las pwn para desencriptar
from pwn import *

#conectamos al servidor
connection = remote('mercury.picoctf.net', 10333)

#recibimos el valor de n
connection.recvuntil("n: ")
n = int(connection.recvline().decode('utf-8'))

#recibimos el valor de e
connection.recvuntil("e: ")
e = int(connection.recvline().decode('utf-8'))

#recibimos el valor del texto cifrado
connection.recvuntil("ciphertext: ")
c = int(connection.recvline().decode('utf-8'))

# se encripta el mensaje, ya que es homomorfico entonces, podemos tomar un valor conocido como 2 y cifrarlo
# realizando 2**e mod n. Para luego calcular este resultado por el cifrado.
m = pow(2, e, n)
enc = str(m * c)
connection.sendline(enc.encode('utf-8'))

#obtenemos la bandera y desencriptamos
connection.recvuntil("go: ")
p = int(connection.recvline().decode('utf-8')) // 2
print(bytes.fromhex(hex(p)[2:]).decode('utf-8'))
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/nopad-noprob]
└─$ python exploiter.py         
[+] Opening connection to mercury.picoctf.net on port 10333: Done
/home/loro/nopad-noprob/exploiter.py:11: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  connection.recvuntil("n: ")
/home/loro/nopad-noprob/exploiter.py:13: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  connection.recvuntil("e: ")
/home/loro/nopad-noprob/exploiter.py:15: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  connection.recvuntil("ciphertext: ")
/home/loro/nopad-noprob/exploiter.py:20: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  connection.recvuntil("go: ")
picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_1772735}
[*] Closed connection to mercury.picoctf.net port 10333
```
### Notas Adicionales

### Referencias
https://play.picoctf.org/practice/challenge/154