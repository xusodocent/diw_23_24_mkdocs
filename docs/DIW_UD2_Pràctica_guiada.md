## Pràctica guiada

Realitza [aquesta](../recursos/ud1/DIW_UD2_P2_1_guiada.pdf)

Has de partir dels següents arxius

``` html
<!DOCTYPE html>
<html lang="es">
    <head>
        <title>Curso HTML5 y CSS3</title>
        <link rel="stylesheet" href="estiloscss3.css">
        <!--[if lt IE 9]>
        <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js">
        </script>
        <![endif]-->
    </head>
    <body>
        <header id="principal">
            <h1>Curso HTML5 y CSS3</h1>
        </header>
    </body>
</html>
```

``` css
body { text-align: center; }

#principal {
    display: block;
    width: 500px;
    margin: 50px auto;
    padding: 15px;
    text-align: center;
    border: 1px solid #999999;
    background: #DDDDDD;
    }

#titulo { font: bold 36px verdana, sans-serif; }
```