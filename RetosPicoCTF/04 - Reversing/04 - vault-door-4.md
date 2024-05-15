## Descripción
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java)

Esta bóveda utiliza codificación ASCII para la contraseña. El código fuente de esta bóveda está aquí: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java)
### Pistas
1. Use a search engine to find an "ASCII table".

1. Utilice un motor de búsqueda para encontrar una "tabla ASCII".
### Solución
```
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-4]
└─$ wget https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java
--2024-04-18 12:18:22--  https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1497 (1.5K) [application/octet-stream]
Saving to: ‘VaultDoor4.java’

VaultDoor4.java              100%[=============================================>]   1.46K  --.-KB/s    in 0s      

2024-04-18 12:18:23 (18.5 MB/s) - ‘VaultDoor4.java’ saved [1497/1497]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0143, 061 ,
            '9' , '4' , 'f' , '7' , '4' , '5' , '8' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
(Como está encriptado en varios lenguajes, vamos a obtener los textos decifrados)
[EN CYBERCHEF]
1. Vamos y pegamos la primera cadena: 106, 85, 53, 116, 95, 52, 95, 98
2. Convertimos con "From Decimal" y nos da: jU5t_4_b
3. Ahora pegamos la segunda cadena: 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f
4. Convertimos con "From Hex" y nos da: UnCh_0f_
5. Pegamos la tercera cadena: 0142, 0131, 0164, 063 , 0163, 0137, 0143, 061
6. Convertimos de "From Octal" con delimitador de "Comma" y nos da: bYt3s_c1
7. La cuarta cadena simplemente son carácteres tipo char, solo hay que agregarlos a la bandera que vamos construyendo y quitarles los "'" para que quede: 94f7458e
8. Lo ponemos en el formato "picoCTF{...}"
[SALIMOS DE CYBERCHEF]
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-4]
└─$ echo "picoCTF{jU5t_4_bUnCh_0f_bYt3s_c194f7458e}"                 
picoCTF{jU5t_4_bUnCh_0f_bYt3s_c194f7458e}
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-4]
└─$ java VaultDoor4.java                                                                            
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_4_bUnCh_0f_bYt3s_c194f7458e}
Access granted.

```
### Notas Adicionales
El código ASCII o simplemente ASCII, es la **codificación utilizada por los sistemas informáticos para representar y leer símbolos, letras, números y funciones a partir del lenguaje de máquina**.
### Referencias
https://play.picoctf.org/practice/challenge/71