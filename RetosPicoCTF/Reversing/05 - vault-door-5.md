## Descripcion
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java)

En el último desafío, dominaste los números octales (base 8), decimales (base 10) y hexadecimales (base 16), ¡pero esta puerta de bóveda utiliza un cambio de base y codificación de URL diferente! El código fuente de esta bóveda está aquí: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java)
### Pistas
1. You may find an encoder/decoder tool helpful, such as https://encoding.tools/
2. Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.

1. Puede que le resulte útil una herramienta de codificación/descodificación, como https://encoding.tools/
2. Lea los artículos de Wikipedia sobre codificación de URL y codificación base 64 para comprender cómo funcionan y cómo se ven los resultados.
### Solución
```
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-5]
└─$ wget https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java
--2024-04-18 12:42:31--  https://jupiter.challenges.picoctf.org/static/0a53bf0deaba6919f98d8550c35aa253/VaultDoor5.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1847 (1.8K) [application/octet-stream]
Saving to: ‘VaultDoor5.java’

VaultDoor5.java              100%[=============================================>]   1.80K  --.-KB/s    in 0s      

2024-04-18 12:42:32 (34.1 MB/s) - ‘VaultDoor5.java’ saved [1847/1847]

                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-5]
└─$ cat VaultDoor5.java
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
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

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTMwJTYyJTM5JTM1JTM3JTYzJTM0JTY2";
        return base64Encoded.equals(expected);
    }
}
(Podemos ver que en el código se convierte primero a URL Encode con una función, luego se pasa a base64 para codificar. Por lo que la bandera está en Base64+URLDec)
[EN CYBERCHEF]
1. Vamos y pegamos las cadenas: JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm
								JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2
								JTM0JTVmJTMwJTYyJTM5JTM1JTM3JTYzJTM0JTY2
2. Agregamos "From Base64" a la receta y nos dará: %63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%30%62%39%35%37%63%34%66
3. Ahora agregamos "URL Decode" a la receta y nos dará: c0nv3rt1ng_fr0m_ba5e_64_0b957c4f
4. Lo ponemos en el formato "picoCTF{...}"
[SALIMOS DE CYBERCHEF]
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-5]
└─$ echo "picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}"
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}
                                                                                                                   
┌──(loro㉿KaliLinux)-[~/vault-doors/vault-door-5]
└─$ java VaultDoor5.java                                                                               
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_0b957c4f}
Access granted.
```
### Notas Adicionales
URL Encoding es una manera en la que las páginas web codifican varios datos de las URL, se puede ver que se compone con %letra o signo.
El Dr. Evil se va a morir de hambre si no le hecha ganas a sus banderas. xd
### Referencias
https://play.picoctf.org/practice/challenge/77