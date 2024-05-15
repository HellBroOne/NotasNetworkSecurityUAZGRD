## Descripción
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java)

¡Esta bóveda utiliza algunas matrices complicadas! Espero que pueda entenderlo, agente especial. El código fuente de esta bóveda está aquí: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java)
### Pistas
1. Look up the charAt() method online.

1. Busca el método charAt() en línea.
### Solución
```
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ wget https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java
--2024-04-17 17:17:35--  https://jupiter.challenges.picoctf.org/static/29b91e638ccbd76aaa8c0462d1c64d8d/VaultDoor1.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2264 (2.2K) [application/octet-stream]
Saving to: ‘VaultDoor1.java’

VaultDoor1.java              100%[=============================================>]   2.21K  --.-KB/s    in 0s      

2024-04-17 17:17:37 (28.4 MB/s) - ‘VaultDoor1.java’ saved [2264/2264]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ head VaultDoor1.java   
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ nano flag
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ nano VaultDoor1.java

┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ nano flag                                                               
[EN NANO LE AGREGAMOS UN 0 A CADA NUMERO DE UN DIGITO]
               password.charAt(00)  == 'd' &&
               password.charAt(29) == '3' &&
               password.charAt(04)  == 'r' &&
               password.charAt(02)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(03)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(01)  == '3' &&
               password.charAt(07)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(05)  == '4' &&
               password.charAt(09)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(08)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(06)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == 'f' &&
               password.charAt(30) == 'b' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '6' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '0'
[SALIMOS DE NANO]
				
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-1]
└─$ cat flag | sort | awk '{print($3)}' | tr -d "'" | tr -d ";" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_ff63b0
```
### Notas Adicionales
El método de charAt ya lo conocíamos, simplemente verifica en base a una cadena de texto que carácter está en una posición dada por los argumentos. Se puede usar para obtener un carácter de una cadena o verificar si está un carácter en una posición.
### Referencias
https://play.picoctf.org/practice/challenge/12