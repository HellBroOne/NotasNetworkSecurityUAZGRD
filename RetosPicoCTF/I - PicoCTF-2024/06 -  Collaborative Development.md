## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

¡Mi equipo ha estado trabajando muy duro en nuevas funciones para nuestro programa de impresión de banderas! Me pregunto cómo trabajarán juntos.Puedes descargar los archivos del reto aquí:
## Pistas
`git branch -a` will let you see available branches
## Solución
```
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso]
└─$ mkdir CollaborativeDevelopment 

                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso]
└─$ cd CollaborativeDevelopment 
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment]
└─$ wget 'https://artifacts.picoctf.net/c_titan/179/challenge.zip'
--2024-03-13 23:49:21--  https://artifacts.picoctf.net/c_titan/179/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.3, 3.161.225.62, 3.161.225.60, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.3|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24648 (24K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip       100%[================>]  24.07K  --.-KB/s    in 0.003s  

2024-03-13 23:49:22 (8.94 MB/s) - ‘challenge.zip’ saved [24648/24648]

                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment]
└─$ ls
challenge.zip
        
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment]
└─$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   ....
   ....
   ....
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment]
└─$ ls
challenge.zip  drop-in
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment]
└─$ cd drop-in 
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ ls
flag.py
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ cat flag.py   
print("Printing the flag...")
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ git branch -a    
  feature/part-1
  feature/part-2
  feature/part-3
* main
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ git diff feature/part-1..feature/part-2
diff --git a/flag.py b/flag.py
index 6e17fb3..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1,2 +1,3 @@
 print("Printing the flag...")
-print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
                                                                             
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ git diff feature/part-1..feature/part-3 
diff --git a/flag.py b/flag.py
index 6e17fb3..c312152 100644
--- a/flag.py
+++ b/flag.py
@@ -1,2 +1,3 @@
 print("Printing the flag...")
-print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
+
+print("w0rk_798f9981}")
                                                                                      
┌──(kali㉿kali)-[~/picoctf/concurso/CollaborativeDevelopment/drop-in]
└─$ 


Flag: picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}

```
## Notas Adicionales
git branch -a: Muestra todas las ramas del repositorio tanto locales como remotas

git diff: Se utiliza para mostrar las diferencias entre los cambios realizados, puede ser de un archivo local a un commit...... entre commits...... o entre branchs.

## Referencias
https://stackoverflow.com/questions/9834689/how-can-i-see-the-differences-between-two-branches
