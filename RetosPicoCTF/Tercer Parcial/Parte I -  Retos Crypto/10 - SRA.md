## Descripción
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...
Additional details will be available after launching your challenge instance. Connect to the program on our server: `nc saturn.picoctf.net 55030`Download the program: [chal.py](https://artifacts.picoctf.net/c/296/chal.py)

Hace poco me enteré del criptosistema de clave pública SRA... o espera, ¿se suponía que era RSA? Hmmm, probablemente debería comprobarlo...
Detalles adicionales estarán disponibles después de lanzar su instancia de desafío.
### Pistas
1. (None)

1. (Ninguna)
### Solución
```
┌──(loro㉿KaliLinux)-[~/sra]
└─$ nc saturn.picoctf.net 55030
anger = 61437678501920602635662236358988286665031932382077155773335201393994293404309
envy = 53927303084331122674300490411880370364266659197714032422199523158718179572113
vainglory?
> yes
yes
Hubris!
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/sra]
└─$ echo "wtf"                                 
wtf
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/sra]
└─$ wget https://artifacts.picoctf.net/c/296/chal.py                                               
--2024-05-14 14:53:35--  https://artifacts.picoctf.net/c/296/chal.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.108, 18.154.132.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 630 [application/octet-stream]
Saving to: ‘chal.py’

chal.py                      100%[==============================================>]     630  --.-KB/s    in 0s      

2024-05-14 14:53:36 (11.2 MB/s) - ‘chal.py’ saved [630/630]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/sra]
└─$ cat chal.py     
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
																												
                                                                                                                    
┌──(loro㉿KaliLinux)-[~/sra]
└─$ mousepad prime_getter.py
^C                                                                                                                    
┌──(loro㉿KaliLinux)-[~/sra]
└─$ pip install primefac   
Defaulting to user installation because normal site-packages is not writeable
Collecting primefac
  Downloading primefac-2.0.12-py3-none-any.whl.metadata (13 kB)
Downloading primefac-2.0.12-py3-none-any.whl (54 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 54.8/54.8 kB 158.2 kB/s eta 0:00:00
Installing collected packages: primefac
Successfully installed primefac-2.0.12
																					                        
																											
┌──(loro㉿KaliLinux)-[~/sra]
└─$ cat prime_getter.py
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

#function to generate all the sub lists
def sub_lists (l):
    #initializing empty list
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
        #Generating sub list
        comb += [list(j) for j in combinations(l, i)]
    #Returning list
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
   #this is dangerous, but I'm trusting me
   return(eval(input()))

#connect to the server
r = remote('saturn.picoctf.net', 59202)
#get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
#get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
#since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
   #multiply them together to get p-1
   for k in l:
      product = product * k
   #if the right length and adding 1 yields a prime, then maybe
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
#try all possible prime pairs
for p in primelist:
   for q in primelist:
      n=p*q
      #decode with this possible n
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
         #see if it corresponds to text and if so, try it
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue
             
┌──(loro㉿KaliLinux)-[~/sra]
└─$ mousepad prime_getter.py
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/sra]
└─$ python3 prime_getter.py 
[+] Opening connection to saturn.picoctf.net on port 59202: Done
/home/loro/sra/prime_getter.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/loro/sra/prime_getter.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 14415438647207494752425834188170581332224050178755386747527847594784035078999
d= 22121670546010190010184453993185490072930796608587074124628519789026806637473
/home/loro/sra/prime_getter.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  1449787922573869822697458561351397462909665617336971076905779301413449826600068000
(Vamos a Prime Factors Decomposition y generamos los numeros primos de este numero)
[2, 2, 2, 2, 2, 3, 3, 5, 5, 5, 7, 109, 2879, 27583, 28608109, 31410900589, 103379063167467163, 7154711760016588149967087810361]
{209018463303032336288039672681747466751, 248659002240437314185083150672216203381, 234100678899396216642604433403557162761, 269427270254707865271518615142863492521, 224522725212256554392932179285719577101, 177613573028883795846487964765868716701}
SV3LZgjiFnYAVqfE
/home/loro/sra/prime_getter.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> SV3LZgjiFnYAVqfE\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}\r\n'
SV3LZgjiFnYAVqfE
[*] Closed connection to saturn.picoctf.net port 59202
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/sra]
└─$ echo "._."
._.
```
### Notas Adicionales
Completamente me basé en la solución de la segunda referencia.
"Se le proporciona un texto cifrado y el valor de d, pero no se le proporciona n. Sabiendo que e * d mod (p-1)(q-1)=1, y que p y q son primos de 128 bits, generamos una lista potencial de valores de p y q, y luego intentamos descifrar con cada uno de los valores posibles. norte. El que sale en texto plano es correcto y luego el programa nos da la clave. Utilicé https://www.dcode.fr/prime-factors-de... para obtener la lista de factores primos."
### Referencias
https://play.picoctf.org/practice/challenge/379
***picoCTF 2023 SRA, by Martin Carlisle:*** https://www.youtube.com/watch?v=3DPWLnrqHZ0
***Prime Factors Decomposition:*** https://www.dcode.fr/prime-factors-decomposition