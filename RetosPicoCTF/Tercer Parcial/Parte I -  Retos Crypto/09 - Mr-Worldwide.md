## Descripción
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

Un músico nos dejó un [mensaje](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). ¿Qué significa?
### Pistas
1. (None)

1. (Ninguna)
### Solución
```
┌──(loro㉿KaliLinux)-[~/mr-worldwide]
└─$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
--2024-05-14 13:53:48--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 278 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                  100%[==============================================>]     278  --.-KB/s    in 0s      

2024-05-14 13:53:49 (7.70 MB/s) - ‘message.txt’ saved [278/278]

                                                                                                                    
┌──(loro㉿KaliLinux)-[~/mr-worldwide]
└─$ cat message.txt
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}

\\Si ingresamos los pares cartesianos en Google Maps se nos da las siguientes ubicaciones:
- Nakanocho, Kamigyō-ku, Kioto, Prefectura de Kioto 602-0958, Japón (Kioto): (35.028309, 135.753082)
- Odesa, Odesa Oblast, Ucrania, 65000 (Odesa): (46.469391, 30.740883)
- Dayton, OH 45402, Estados Unidos (Dayton): (39.758949, -84.191605)
- Hoca Paşa, 34110 Fatih/Provincia de Estambul, Turquía (Istambul): (41.015137, 28.979530)
- Hazza ' Bin Zayed The First St - Al Manhal - Abu Dhabi - Emiratos Árabes Unidos (Abu Dhabi): (24.466667, 54.366669)
- Room 11, Level 2, Bangunan Sulaiman, Jalan Sultan Hishamuddin, 50000 Kuala Lumpur, Malasia (Kuala Lumpur): (3.140853, 101.693207)
- Kirkos, Adís Abeba, Etiopía (Adis Abeba): (9.005401, 38.763611)
- Av. Nueva Loja, Loja, Ecuador (Loja): (-3.989038, -79.203560)
- Martelaarsgracht 5, 1012 TM Amsterdam, Países Bajos (Amsterdam): (52.377956, 4.897070)
- Sleepy Hollow, NY 10591, Estados Unidos (Sleepy Hollow): (41.085651, -73.858467)
- QHRV+242 Kodiak, Alaska, EE. UU. (Kodiak): (57.790001, -152.407227)
- Faculty Of Engineering, Al Azaritah WA Ash Shatebi, Bab Sharqi, Alexandria Governorate 5423021, Egipto (Alexandria): (31.205753, 29.924526)

\\Si nos ponemos a analizar las primeras letras de las regiones, o ciudades (las encerradas entreparentesis) podremos ver que se tiene la siguiente oracion: 
	- [K]ioto
	- [O]desa
	- [D]ayton
	- [I]stambul (Estambul en ingles)
	- [A]bu Dhabi 
	- [K]uala Lumpur
	- _
	- [A]dis Abeba
	- [L]oja
	- [A]msterdam
	- [S]leepy Hollow
	- [K]odiak
	- [A]lexandria
\\Y sustituyendo el texto que se nos dio al hacer el "cat" al mensaje, nos da como resultado que la bandera es: picoCTF{KODIAK_ALASKA}
```
### Notas Adicionales
Alaskaguamas.
### Referencias
https://play.picoctf.org/practice/challenge/40