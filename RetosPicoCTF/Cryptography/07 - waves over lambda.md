## Descripcion
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 43522`.

Hicimos muchas sustituciones para cifrar esto. ¿Puedes descifrarlo? Conéctese con `nc jupiter.challenges.picoctf.org 43522`.
### Pistas
1. Flag is not in the usual flag format

1. La bandera no tiene el formato habitual
### Solución
```
┌──(loro㉿KaliLinux)-[~]
└─$ nc jupiter.challenges.picoctf.org 43522.
-------------------------------------------------------------------------------
sftlgwrh akgk ch efjg qxwl - qgkojktse_ch_s_fikg_xwymbw_flqywjtgwq
-------------------------------------------------------------------------------
nk nkgk tfr yjsa yfgk rawt w ojwgrkg fq wt afjg fjr fq fjg hacp rcxx nk hwn akg hctz, wtb rakt c jtbkghrffb qfg rak qcghr rcyk nawr nwh ykwtr me w hacp qfjtbkgctl ct rak hkw.  c yjhr wsztfnxkblk c awb awgbxe kekh rf xffz jp nakt rak hkwykt rfxb yk hak nwh hctzctl; qfg qgfy rak yfyktr rawr rake gwrakg pjr yk ctrf rak mfwr rawt rawr c yclar mk hwcb rf lf ct, ye akwgr nwh, wh cr nkgk, bkwb ncract yk, pwgrxe ncra qgclar, pwgrxe ncra afggfg fq yctb, wtb rak rafjlarh fq nawr nwh ekr mkqfgk yk.

Para este texto vamos a Substitution Solver.
1. Pegamos el texto en Substitution Solver
2. Hacemos clic en "Break Cipher"
3. Podemos obtener la bandera: frequency_is_c_over_lambda_ogfmaunraf
```
### Notas Adicionales
### Referencias
https://play.picoctf.org/practice/challenge/38
**Substitution Solver:** https://www.guballa.de/substitution-solver