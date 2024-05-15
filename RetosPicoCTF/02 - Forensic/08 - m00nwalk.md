## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

Decodifica este [mensaje](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) de la luna.
### Pistas
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option.

1. ¿Cómo se enviaron a la Tierra las imágenes del alunizaje?
2. ¿Cuál es la mascota de CMU?, eso podría ayudar a seleccionar una opción de RX.
### Solución
```
(kali㉿kali)-[~/picoctf/forensic/parte2]$ cd m00nwalk

(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ wget 'https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav'

--2024-03-19 14:14:42--  https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’
message.wav           100%[======================>]  10.55M  3.23MB/s    in 3.4s   
2024-03-19 14:14:46 (3.10 MB/s) - ‘message.wav’ saved [11066998/11066998]

(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ file message.wav
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ sstv -d message.wav -o img.jpg                      
[sstv] Searching for calibration header... Found!   
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [####################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ ls
img.jpg  message.wav
(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ fim img.jpg
(kali㉿kali)-[~/picoctf/forensic/parte2/m00nwalk]$ picoCTF{beep_boop_im_in_space}
```
### Notas Adicionales
En este reto aprendimos a decodificar videos con sstv, y permite obtener un espectrograma de un archivo de música mediante sus ondas, es así como obtenemos la imagen.
### Referencias
https://play.picoctf.org/practice/challenge/26
***Más sobre Apollo:*** https://en.wikipedia.org/wiki/Apollo_11_missing_tapes