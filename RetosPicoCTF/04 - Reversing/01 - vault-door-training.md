## Descripción
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)

Tu misión es ingresar al laboratorio del Dr. Evil y recuperar los planos de su Proyecto Doomsday. El laboratorio está protegido por una serie de puertas de bóveda cerradas con llave. Cada puerta está controlada por una computadora y requiere una contraseña para abrirse. Desafortunadamente, nuestros agentes encubiertos no han podido obtener las contraseñas secretas de las puertas de la bóveda, ¡pero uno de nuestros agentes junior obtuvo el código fuente de la computadora de cada bóveda! Deberá leer el código fuente de cada nivel para descubrir cuál es la contraseña para la puerta de esa bóveda. Como calentamiento, hemos creado una réplica del salto en nuestras instalaciones de entrenamiento. El código fuente de la bóveda de entrenamiento está aquí: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)
### Pistas
1. The password is revealed in the program's source code.

1. La contraseña se revela en el código fuente del programa.
### Solución
```
1. Abrimos el código:
import java.util.*;  
  
class VaultDoorTraining {  
    public static void main(String args[]) {  
        VaultDoorTraining vaultDoor = new VaultDoorTraining();  
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
  
    // The password is below. Is it safe to put the password in the source code?  
    // What if somebody stole our source code? Then they would know what our    // password is. Hmm... I will think of some ways to improve the security    // on the other doors.    //    // -Minion #9567    public boolean checkPassword(String password) {  
        return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");  
    }  
}
2. El password de la función checkpassword esta en el parámetro de la función.
3. La bandera es picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}
```
### Notas Adicionales
Java es un lenguaje de programación y una plataforma informática que fue comercializada por primera vez en 1995 por Sun Microsystems.​​ 
Teniendo un código fuente es posible verificar el funcionamiento de este código.
### Referencias
https://play.picoctf.org/practice/challenge/7