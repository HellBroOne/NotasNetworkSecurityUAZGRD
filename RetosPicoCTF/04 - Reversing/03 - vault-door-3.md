## Descripción
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java)

Esta bóveda utiliza bucles for y arreglos de bytes. El código fuente de esta bóveda está aquí: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java)
### Pistas
1. Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

1. Crea una tabla que contenga cada valor de las variables del bucle y el índice del búfer correspondiente en el que escribe.
### Solución
```
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ wget https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java
--2024-04-17 17:32:27--  https://jupiter.challenges.picoctf.org/static/a648ca6dd275b9454c5d0de6d0f6efd3/VaultDoor3.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1474 (1.4K) [application/octet-stream]
Saving to: ‘VaultDoor3.java’

VaultDoor3.java                                            100%[========================================================================================================================================>]   1.44K  --.-KB/s    in 0s      

2024-04-17 17:32:31 (25.8 MB/s) - ‘VaultDoor3.java’ saved [1474/1474]

                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ cat VaultDoor3.java                                                     
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");
    }
}
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ java VaultDoor3.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{U5t_a_sna_3lpm18gb41_u_4_mfr340}
Access denied!
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ java VaultDoor3.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_a_sna_3lpm18gb41_u_4_mfr340}
Access denied!
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ nano VaultDoor3.java
[EN NANO, yo simplemente imprimi el string resultante en vez de ver los for]
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        System.out.println(s); <<< Agregué eso.
        return s.equals("jU5t_a_sna_3lpm18gb41_u_4_mfr340");
    }
}

[SALIMOS DE NANO]
                                                                                                                                                                                                                                            
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3]
└─$ java VaultDoor3.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_a_sna_3lpm18gb41_u_4_mfr340}
jU5t_a_s1mpl3_an4gr4m_4_u_1fb380
Access denied!
                                                                                                                                                                                                                                              
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-3] 
└─$ java VaultDoor3.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}   
jU5t_a_sna_3lpm18gb41_u_4_mfr340
Access granted.
```
### Notas Adicionales
Un array es una **estructura de datos que nos permite almacenar una serie de datos de un mismo tipo**. 
El for loop **permite a una aplicación Java realizar una acción hasta que se cumpla una condición previamente definida**.
### Referencias
https://play.picoctf.org/practice/challenge/60