## Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/26704/` ([link](https://jupiter.challenges.picoctf.org/problem/26704/)) or http://jupiter.challenges.picoctf.org:26704

Este sitio web solo se puede representar mediante **picobrowser**, ¡ve y atrapa la bandera! `https://jupiter.challenges.picoctf.org/problem/26704/` ([enlace](https://jupiter.challenges.picoctf.org/problem/26704/)) o http://jupiter.challenges. picoctf.org:26704
### Pistas
1. You don't need to download a new web browser
### Solución
1. Hay que entrar al link de https://jupiter.challenges.picoctf.org/problem/26704/
2. Presionamos en "Flag" y no nos dejará entrar. (https://jupiter.challenges.picoctf.org/problem/26704/flag)
3. Copiamos el link después de haber clickeado el botón de la bandera.
4. Escribir lo siguiente en la shell de linux:
```
hellbroone-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/26704/flag -H "User-Agent: picobrowser" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0   5850      0 --:--:-- --:--:-- --:--:--  5842
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}</code></p>
hellbroone-picoctf@webshell:~$
```
### Notas Adicionales
No es necesario descargar un nuevo cliente de pico browser, si no que hay que darle la idea al sitio que estamos usando "picobrowser", para ello usamos curl y en el header especificamos "User-Agent" para especificar que estamos en Pico.
### Referencias
https://play.picoctf.org/practice/challenge/69
https://jupiter.challenges.picoctf.org/problem/26704/flag
