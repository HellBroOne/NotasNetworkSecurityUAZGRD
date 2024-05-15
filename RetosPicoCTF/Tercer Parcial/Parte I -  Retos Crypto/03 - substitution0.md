## Descripción
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://artifacts.picoctf.net/c/153/message.txt).

Ha llegado un mensaje pero parece estar todo codificado. Por suerte parece tener la clave al principio. ¿Puedes descifrar este cifrado de sustitución? Descargue el mensaje [aquí](https://artifacts.picoctf.net/c/153/message.txt).
### Pistas
1. Try a frequency attack. An online tool might help.

1. Pruebe un ataque de frecuencia. Una herramienta en línea podría ayudar.
### Solución
```
1. Descargamos el archivo txt del reto.
2. Al hacer un "cat" se muestra que el texto contiene lo siguiente:
	OHNFUMWSVZLXEGCPTAJDYIRKQB 
	
	Suauypcg Xuwaogf oacju, rvds o waoiu ogf jdoduxq ova, ogf hacywsd eu dsu huudxu
	mace o wxojj noju vg rsvns vd roj ugnxcjuf. Vd roj o huoydvmyx jnoaohouyj, ogf, od
	dsod dveu, yglgcrg dc godyaoxvjdj—cm ncyaju o wauod pavbu vg o jnvugdvmvn pcvgd
	cm ivur. Dsuau ruau drc acygf hxonl jpcdj guoa cgu ukdauevdq cm dsu honl, ogf o
	xcgw cgu guoa dsu cdsua. Dsu jnoxuj ruau uknuufvgwxq soaf ogf wxcjjq, rvds oxx dsu
	oppuoaognu cm hyagvjsuf wcxf. Dsu ruvwsd cm dsu vgjund roj iuaq aueoalohxu, ogf,
	dolvgw oxx dsvgwj vgdc ncgjvfuaodvcg, V ncyxf soafxq hxoeu Zypvdua mca svj cpvgvcg
	aujpundvgw vd.
	
	Dsu mxow vj: pvncNDM{5YH5717Y710G_3I0XY710G_03055505}
3. Para esto debemos hacer uso de una herramienta de ataque de frecuencia, en este caso utilizare la de "Mono-alphabetic Substitution"
4. Pegamos el texto en el cuadro de texto y hacemos clic en "Decrypt Automatically"
5. Se nos da el siguiente texto:
HEREUPON LEGRAND AROSE, WITH A GRAVE AND STATELY AIR, AND BROUGHT ME THE BEETLE FROM A GLASS CASE IN WHICH IT WAS ENCLOSED. IT WAS A BEAUTIFUL SCARABAEUS, AND, AT THAT TIME, UNKNOWN TO NATURALISTS--OF COURSE A GREAT PRIZE IN A SCIENTIFIC POINT OF VIEW. THERE WERE TWO ROUND BLACK SPOTS NEAR ONE EXTREMITY OF THE BACK, AND A LONG ONE NEAR THE OTHER. THE SCALES WERE EXCEEDINGLY HARD AND GLOSSY, WITH ALL THE APPEARANCE OF BURNISHED GOLD. THE WEIGHT OF THE INSECT WAS VERY REMARKABLE, AND, TAKING ALL THINGS INTO CONSIDERATION, I COULD HARDLY BLAME QUPITER FOR HIS OPINION RESPECTING IT. 
THE FLAG IS: PICOCTF{5UB5717U710N_3V0LU710N_03055505}
6. La bandera al final es: picoCTF{5UB5717U710N_3V0LU710N_03055505}
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/307
***Mono-alphabetic Substitution:*** https://www.dcode.fr/frequency-analysis