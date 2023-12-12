## Mapa de colors per a botons

Crea un fitxer Sass anomenat styles.scss que defineix estils per a botons de diferents colors. Utilitza variables per als colors, nidament per estructurar el codi, el símbol «&» per crear estils específics per a cada botó i mapes per emmagatzemar informació sobre els colors dels botons.

```html
<button class="button primary">Botón Primario</button>
<button class="button success">Botón de Éxito</button>
<button class="button danger">Botón de Peligro</button>
```

```scss
// Define variables para los colores de los botones
$primary-color: #3498db;
$success-color: #27ae60;
$danger-color: #e74c3c;

// Define un mapa para los estilos de los botones
$button-styles: (
  primary: (
    background-color: $primary-color,
    color: white,
  ),
  success: (
    background-color: $success-color,
    color: white,
  ),
  danger: (
    background-color: $danger-color,
    color: white,
  ),
);
// Estilos generales de los botones
.button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  margin: 5px;
  transition: background-color 0.3s ease;

  &:hover {
    background-color: darken($primary-color, 10%);
  }
}

// Estilos específicos para cada botón
@each $button, $style in $button-styles {
  .#{$button} {
    background-color: map-get($style, background-color);
    color: map-get($style, color);

    &:hover {
      background-color: darken(map-get($style, background-color), 10%);
    }
  }
}
```

Resultat...

```css

  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  margin: 5px;
  transition: background-color 0.3s ease;
}
.button:hover {
  background-color: #217dbb;
}

.primary {
  background-color: #3498db;
  color: white;
}
.primary:hover {
  background-color: #217dbb;
}

.success {
  background-color: #27ae60;
  color: white;
}
.success:hover {
  background-color: #1e8449;
}

.danger {
  background-color: #e74c3c;
  color: white;
}
.danger:hover {
  background-color: #d62c1a;
}
```

## Caixes de colors

Crea un archivo Sass llamado «styles.scss» que genere estilos para una serie de cajas con colores de fondo diferentes utilizando un bucle @for en Sass. Utiliza la función darken() para oscurecer las cajas al parar el cursor por encima.

```html
<div class="caja caja-1"></div>
<div class="caja caja-2"></div>
<div class="caja caja-3"></div>
<div class="caja caja-4"></div>
<div class="caja caja-5"></div>
<div class="caja caja-6"></div>
<div class="caja caja-7"></div>
<div class="caja caja-8"></div>
<div class="caja caja-9"></div>
<div class="caja caja-10"></div>
```

```scss
// Define una variable para la cantidad de cajas que deseas crear
$num-cajas: 10;
// Define una lista de colores de fondo predefinidos
$colores-fondo: #3498db, #27ae60, #e74c3c, #9b59b6, #f1c40f, #2ecc71, #e67e22, #1abc9c, #34495e, #d35400;
// Define una variable para el tamaño de cada caja
$tamano-caja: 100px;
// Estilos generales de las cajas
.caja {
  width: $tamano-caja;
  height: $tamano-caja;
  margin: 10px;
  display: inline-block;
}
// Utiliza un bucle @for para generar cajas con colores de fondo diferentes
@for $i from 1 through $num-cajas {
  $color-fondo: nth($colores-fondo, $i); // Obtiene un color de fondo de la lista
  .caja-#{$i} {
      background-color: $color-fondo;
    // Aplicamos color de fondo más oscuro al pasar por encima el cursor
      &:hover {
        background-color: darken($color-fondo, 10%);
      }
  }
}
```

