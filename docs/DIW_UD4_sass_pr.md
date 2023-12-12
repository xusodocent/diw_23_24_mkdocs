## Botiga online

Has de partir d'aquest html que no pots modificar...

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="estils.css">
</head>

<body>
    <h1>Mi tienda online</h1>
    <p>Explora nuestros productos y ofertas exclusivas.</p>
    <button class="primary-button">Ver Productos</button>
    <button class="secondary-button">Registrarse</button>
    <h2>Destacados</h2>
    <div class="product">
        <img src="https://cdn-icons-png.flaticon.com/128/4990/4990734.png" alt="Prod 1">
        <h3>Producto 1</h3>
        <p>Descripción del Producto 1.</p>
        <p class="important-text">$19.99</p>
        <button class="buy-button">Comprar</button>
    </div>
    <div class="product">
        <img src="https://cdn-icons-png.flaticon.com/128/4990/4990734.png" alt="Prod 2">
        <h3>Producto 2</h3>
        <p>Descripción del Producto 2.</p>
        <p class="important-text">$24.99</p>
        <button class="buy-button">Comprar</button>
    </div>
    <div class="product centered">
        <img src="https://cdn-icons-png.flaticon.com/128/4990/4990734.png" alt="Prod 3">
        <h3>Producto 3</h3>
        <p>Descripción del Producto 3.</p>
        <p class="important-text">$29.99</p>
        <button class="buy-button">Comprar</button>
    </div>
</body>

</html>
```

Per a obtindre aquest resultat...

![botiga online](./img/botigaonline.png)

Fes les següents accions...

Crea un fitxer SCSS anomenat `styles.scss`.

Defineix les variables següents al teu fitxer SCSS:

`$primary-color`: #3498db
`$secondary-color`: #e74c3c
`$font-family`: Arial
`$base-font-size`: 16px

Aplica els estils següents:

El fons del body és de color #f2f2f2, la font de tipus $font-family, i el text alineat al centre.

El títol `<h1>` ha de tenir una mida de font de 2rem i utilitzar el color definit a $primary-color.
    
Els paràgrafs `<p>` han de tenir una mida de font de 1.2rem i utilitzar un color gris fosc (#555).

Els botons han de tenir un padding de 10px 20px, sense vores, un radi de vora de 5px, un marge de 10px i una transició suau de 0.3s per al canvi de color de fons en lefecte hover.

`.product` Els productes tenen un fons blanc, una vora sòlida de 1px, un radi de vora de 5px, un marge de 10px i un ombrejat subtil en hover.
    
`<img>` Les imatges dels productes han de tenir una amplada màxima del 100% i una alçada automàtica.
    
`<h3>` Els títols dels productes han de tenir una mida de font de 1.5rem.

`.important-tex` Els preus dels productes amb la classe .important-text han de tenir la font en negreta i un color definit a `$secondary-color`.

Defineix un mapa anomenat `$button-styles` que emmagatzemi estils per a botons. Cada entrada al mapa ha de tenir els següents noms i valors:
        primary-button → $primary-color
        secondary-button → #2ecc71
        buy-button → #f39c12

Crea un mixin anomenat `center-element` que permeti centrar elements tant horitzontal com verticalment. Pots fer servir Flexbox.

Utilitza un bucle `@each` per recórrer el mapa `$button-styles` i crear les classes `.primary-button`, .`secondary-button` i `.buy-button`. Cada classe tindrà un color de fons igual al color corresponent del mapa $button-styles. Aplica als botons una funció darken del 10% per enfosquir el color en fer hover.

Crea la classe `.centered` per centrar el darrer producte. Utilitza el mixin 'center-element' creat anteriorment. Usa la paraula clau @include seguida del nom del mixin.