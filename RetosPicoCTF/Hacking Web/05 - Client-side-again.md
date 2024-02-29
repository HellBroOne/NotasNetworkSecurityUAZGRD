## Descripcion
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/56816/` ([link](https://jupiter.challenges.picoctf.org/problem/56816/)) or http://jupiter.challenges.picoctf.org:56816

¿Podrás entrar en este portal súper seguro? `https://jupiter.challenges.picoctf.org/problem/56816/` ([enlace](https://jupiter.challenges.picoctf.org/problem/56816/)) o http://jupiter.challenges. picoctf.org:56816
### Pistas
1. What is obfuscation?
### Solución
1. Hay que entrar al link de http://jupiter.challenges.picoctf.org:56816
2. Inspeccionamos el elemento y obtenemos el siguiente fragmento del javascript:
```
var _0x5a46=['37115}','_again_3','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];(function(_0x4bd822,_0x2bd6f7){var _0xb4bdb3=function(_0x1d68f6){while(--_0x1d68f6){_0x4bd822['push'](_0x4bd822['shift']());}};_0xb4bdb3(++_0x2bd6f7);}(_0x5a46,0x1b3));var _0x4b5b=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x5a46[_0x2d8f05];return _0x4d74cb;};function verify(){checkpass=document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];split=0x4;if(checkpass[_0x4b5b('0x2')](0x0,split*0x2)==_0x4b5b('0x3')){if(checkpass[_0x4b5b('0x2')](0x7,0x9)=='{n'){if(checkpass[_0x4b5b('0x2')](split*0x2,split*0x2*0x2)==_0x4b5b('0x4')){if(checkpass[_0x4b5b('0x2')](0x3,0x6)=='oCT'){if(checkpass[_0x4b5b('0x2')](split*0x3*0x2,split*0x4*0x2)==_0x4b5b('0x5')){if(checkpass['substring'](0x6,0xb)=='F{not'){if(checkpass[_0x4b5b('0x2')](split*0x2*0x2,split*0x3*0x2)==_0x4b5b('0x6')){if(checkpass[_0x4b5b('0x2')](0xc,0x10)==_0x4b5b('0x7')){alert(_0x4b5b('0x8'));}}}}}}}}else{alert(_0x4b5b('0x9'));}}
```
3. Obtenemos la parte de:
```
var _0x5a46=['37115}','_again_3','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];
```
5. Entramos a la consola del sitio web y la pegamos como: 
```
var nueva =['37115}','_again_3','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];
```
6. Verificamos cuál es la contraseña:
```
nueva[8] + nueva[9] + nueva[1] + nueva[0]
```
	y la obtenemos.
### Notas Adicionales
Para este reto tuvimos que hacer una inspección a un sitio web mediante el código fuente, el javascript y el css.
Simplemente hay que entrar al inspector de páginas web y encontrar la parte necesaria.
### Referencias
https://play.picoctf.org/practice/challenge/69
https://jupiter.challenges.picoctf.org/problem/56816/
