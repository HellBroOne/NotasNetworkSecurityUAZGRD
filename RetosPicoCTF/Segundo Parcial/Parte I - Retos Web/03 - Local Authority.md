## Descripcion
Can you get the flag? Go to this [website](http://saturn.picoctf.net:59126/) and see what you can discover.

¿Puedes conseguir la bandera? Vaya a este [sitio web](http://saturn.picoctf.net:59126/) y vea lo que puede descubrir.
### Pistas
1. How is the password checked on this website?

1. ¿Cómo se comprueba la contraseña en este sitio web?
### Solución
```
1. Abrimos el sitio e ingresamos cualquier cosa en el usuario y password
2. Nos redirijirá a una página de "Log In Failed"
3. Hacemos clic derecho y hacemos clic en "Inspeccionar"
4. Vemos que abajo hay un código que dice:
  function filter(string) { 
	  filterPassed = true; 
	  for (let i =0; i < string.length; i++){ cc = string.charCodeAt(i); 
		  if ( (cc >= 48 && cc <= 57) || (cc >= 65 && cc <= 90) || (cc >= 97 && cc <= 122) ) { 
			  filterPassed = true; 
		  } else { 
			  return false; 
		  } 
		} 
		return true; 
	} 
  window.username = "caca"; 
  window.password = ""; 
  usernameFilterPassed = filter(window.username); 
  passwordFilterPassed = filter(window.password); 
  if ( usernameFilterPassed && passwordFilterPassed ) { 
	  loggedIn = checkPassword(window.username, window.password); 
	  if(loggedIn) { 
		  document.getElementById('msg').innerHTML = "Log In Successful";
		  document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";
		  document.getElementById('hiddenAdminForm').submit(); 
	  } else { 
		  document.getElementById('msg').innerHTML = "Log In Failed"; 
	  } 
  } else { 
	  document.getElementById('msg').innerHTML = "Illegal character in username or password." 
  }
5. Obviamente no vamos a ponernos a hacerle una ingeniería inversa a esto, pero es fácil ver que en una parte del código se hace referencia a la función de "checkPassword" que no está en el script.
6. Viendo el código de HTML se puede ver que se hace uso del script "secure.js", lo abrimos yendo a la parte de "Sources" o "Fuentes".
7. Podemos ver que hay una verificación en el código:
	function checkPassword(username, password){
		if( username == 'admin' && password == 'strongPassword098765' )
		...
8. Q babos.. que diga, aquí ya descubrimos que cuales son los usuarios y contraseñas correctas. Las ingresamos en la página anterior.
9. Al hacer inicio de sesión, se nos dará la bandera automáticamente: picoCTF{j5_15_7r4n5p4r3n7_a8788e61}
```
### Notas Adicionales
Gracias al inspector de elementos se nos es posible ver el código js de una página web, quizá sirve para ver las funciones de dicha página y poder guiarnos en el comportamiento de esta.
No hay que dejar una contraseña en un if por que luego nos hackean.
### Referencias
https://play.picoctf.org/practice/challenge/278