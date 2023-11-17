## Pre-processadors CSS

!!! note "Que són?"

    Els preprocessadors de CSS són eines que permeten als desenvolupadors escriure codi CSS amb una sintaxi més rica i avançada, i després compilar-lo a codi CSS convencional que pot ser interpretat pel navegador web. Aquesta compilació permet utilitzar característiques que no estan disponibles de manera nativa en CSS, com ara variables, mixins, seleccions aninhades i altres funcions que faciliten la creació i el manteniment del codi estil.

Hi ha diversos preprocessadors de CSS populars, i alguns dels més coneguts són:

1. **Sass (Syntactically Awesome Stylesheets):** Sass és un dels preprocessadors de CSS més antics i populars. Proporciona una sintaxi més concisa i poderosa que CSS, amb funcionalitats com variables, mixins, seleccions aninhades i importació de fitxers.

2. **SCSS (Sassy CSS):** SCSS és una sintaxi alternativa per a Sass que es basa en la sintaxi de CSS convencional. Això significa que tot el CSS vàlid també és vàlid a SCSS. SCSS ofereix les mateixes funcionalitats que Sass però amb una sintaxi que pot ser més familiar per als desenvolupadors acostumats a CSS.

3. **Less:** Less és un altre preprocessador de CSS que ofereix funcionalitats similars a Sass i SCSS, com ara variables, mixins, seleccions aninhades i operacions aritmètiques. Utilitza una sintaxi pròpia diferent de CSS.

4. **Stylus:** Stylus és un preprocessador de CSS amb una sintaxi minimalista i flexible. Intenta mantenir la sintaxi tan senzilla com sigui possible, permetent l'ús d'opcions abreviades i ometent algunes de les paraules clau de CSS.

En resum, els preprocessadors de CSS ofereixen eines poderoses per millorar la manera com s'escriu i es gestiona el codi estil. Aquestes eines permeten una millor organització, reutilització de codi i proporcionen funcionalitats avançades que faciliten el desenvolupament web. La majoria d'aquestes sintaxis són posteriorment compilades a CSS per a la seva implementació en un entorn de producció.


## SASS

`Sass` és un acrònim que significa =="Syntactically Awesome Stylesheets"==. És un llenguatge de fulls d'estil dissenyat per millorar l'eficiència i la llegibilitat del codi CSS. 

!!! warning "Compilació"

    Sass es pre-processa abans que s'apliquin els estils al lloc web, la qual cosa significa que has de compilar-lo a CSS abans de implementar-lo en un projecte.

Algunes de les característiques clau de Sass inclouen:

1. **Variables:** Pots definir variables per emmagatzemar valors i reutilitzar-les a tot el teu codi.

2. **Anidament:** Pots anidar selectors de manera similar a l'estructura HTML, la qual cosa fa que el codi sigui més fàcil d'entendre.

3. **Mixins:** Els mixins et permeten reutilitzar blocs de codi en diferents parts del teu full d'estil.

4. **Herència:** Pots crear estils base i després estendre'ls a través d'herència, facilitant la gestió d'estils similars.

5. **Funcions:** Sass inclou funcions que permeten realitzar operacions i manipulacions més avançades en els teus estils.

6. **Importació:** Pots dividir el teu codi en diversos fitxers i després importar-los en un fitxer principal, facilitant l'organització del codi.

Aquestes característiques fan que Sass sigui una eina poderosa per a desenvolupadors web en millorar la modularitat, la llegibilitat i la reutilització del codi en comparació amb l'ús directe de CSS.

### Instal·lació

Per instal·lar Sass a Ubuntu 22.04, pots seguir els passos següents:

1. **Actualitzar el sistema:**
   Abre una terminal i executa els següents comandaments per assegurar-te que el sistema està actualitzat:

   ```bash
   sudo apt update
   sudo apt upgrade
   ```

2. **Instal·lar Ruby:**
   Sass es basa en Ruby, així que necessitaràs tenir Ruby instal·lat. Executa aquests comandaments:

   ```bash
   sudo apt install ruby-full
   ```

3. **Instal·lar Sass:**
   Una vegada que Ruby està instal·lat, pots utilitzar la gem (el sistema de gestió de paquets de Ruby) per instal·lar Sass:

   ```bash
   sudo gem install sass
   ```

4. **Verificar la instal·lació:**
   Pots comprovar si Sass s'ha instal·lat correctament executant:

   ```bash
   sass --version
   ```

   Això hauria de mostrar la versió de Sass instal·lada al teu sistema.

Amb aquests passos, hauries d'haver instal·lat Sass al teu sistema Ubuntu 22.04. Pots començar a utilitzar-lo per preprocessar els teus arxius Sass i generar els corresponents arxius CSS.

### Compilar

Per compilar arxius Sass a CSS, utilitzes la comanda `sass` a la línia de comandes. Aquí tens alguns exemples senzills:

#### 1. Compilar un fitxer Sass a un fitxer CSS:

```bash
sass input.scss output.css
```

On `input.scss` és el teu fitxer Sass d'origen i `output.css` és el nom del fitxer CSS que vols generar.

#### 2. Compilar i observar canvis:

Per evitar haver de compilar manualment cada vegada que fas un canvi, pots utilitzar l'opció `--watch`. Això farà que Sass estigui en mode observació i compili automàticament quan es detectin canvis al fitxer Sass.

```bash
sass --watch input.scss:output.css
```

Ara, qualsevol canvi que facis a `input.scss` es detectarà i es compilarà automàticament a `output.css`.

#### 3. Compilar tots els fitxers Sass d'un directori:

Si tens diversos fitxers Sass en un directori i vols compilar-los tots a CSS, pots fer-ho de la següent manera:

```bash
sass --watch input-dir:output-dir
```

On `input-dir` és el directori que conté els fitxers Sass i `output-dir` és el directori on es generaran els fitxers CSS corresponents.

Amb aquestes comandes, pots començar a utilitzar Sass per gestionar els teus fitxers d'estil de manera més eficient i utilitzar les característiques addicionals que Sass ofereix, com ara variables, mixins i anidament.

A continuació es mostra un exemple del codi que genera scss.

=== "scss"
    ``` scss
        /* Define standard variables and values for website */
        $bgcolor: lightblue;
        $textcolor: darkblue;
        $fontsize: 18px;

        /* Use the variables */
        body {
        background-color: $bgcolor;
        color: $textcolor;
        font-size: $fontsize;
        }                  
    ```

=== "css"
    ``` css
        body {
        background-color: lightblue;
        color: darkblue;
        font-size: 18px;
        }
    ```


### Variables

!!! info "Ús"
    A Sass, les variables són elements fonamentals que et permeten emmagatzemar i reutilitzar valors en tot el teu codi. Pots definir variables per emmagatzemar colors, dimensions, marges, o qualsevol valor que vulguis utilitzar repetidament. Aquesta funcionalitat ajuda a fer el teu codi més mantenible i flexible. 

=== "scss"
    ```scss
        $myFont: Helvetica, sans-serif;
        $myColor: red;
        $myFontSize: 18px;
        $myWidth: 680px;

        body {
        font-family: $myFont;
        font-size: $myFontSize;
        color: $myColor;
        }

        #container {
        width: $myWidth;
        }
    ```

=== "css"
    ``` css
        body {
        font-family: Helvetica, sans-serif;
        font-size: 18px;
        color: red;
        }

        #container {
        width: 680px;
        }
    ```

#### Scope

El concepte de "scope" (àmbit o context) en les variables de Sass es refereix a la disponibilitat o visibilitat d'una variable en un determinat àmbit del teu codi. En Sass, el scope d'una variable depèn d'on es defineixi.

Hi ha dos tipus principals d'àmbits en Sass:

1. **Àmbit global:** Quan defines una variable fora de qualsevol bloc o regla, aquesta té àmbit global i es pot utilitzar en tot el teu fitxer Sass.

   Exemple:

   ```scss
   $color-primary: #3498db;

   body {
     background-color: $color-primary;
   }

   h1 {
     color: $color-primary;
   }
   ```

   En aquest exemple, `$color-primary` és una variable amb àmbit global, i es pot utilitzar tant a la regla `body` com a la regla `h1`.

2. **Àmbit local:** Quan defines una variable dins d'una regla, mixin o funció, aquesta té àmbit local i només és accessible dins del bloc on es va definir.

   Exemple:

   ```scss
   body {
     $font-size-heading: 24px;
     font-size: $font-size-heading;
   }

   p {
     // La següent línia generaria un error perquè $font-size-heading no és visible aquí.
     // font-size: $font-size-heading;
   }
   ```

   En aquest exemple, `$font-size-heading` té àmbit local a la regla `body`, així que no es pot utilitzar fora d'aquest bloc.

És important tenir en compte aquesta distinció d'àmbits, ja que pot afectar la manera com les variables es reutilitzen i es mantenen en el teu codi Sass. Si necessites que una variable tingui àmbit global, has de definir-la fora de qualsevol bloc o regla. Si vols que tingui àmbit local, la pots definir dins del bloc pertinent.


#### Nestings

El nesting, o anidament, en Sass fa referència a la capacitat d'encadenar selectors dins d'altres selectors per reflectir la jerarquia de l'estructura HTML directament al teu codi Sass. Això fa que el codi sigui més llegible i reflecteixi de manera més clara la relació entre els elements. 

=== "scss"
    ```scss
        nav {
            ul {
                margin: 0;
                padding: 0;
                list-style: none;
            }
            li {
                display: inline-block;
            }
            a {
                display: block;
                padding: 6px 12px;
                text-decoration: none;
            }
        }
    ```

=== "css"
    ``` css
        nav ul {
        margin: 0;
        padding: 0;
        list-style: none;
        }
        nav li {
        display: inline-block;
        }
        nav a {
        display: block;
        padding: 6px 12px;
        text-decoration: none;
        }
    ```

#### @import

!!! note "Que és?"

    La directiva `@import` en Sass s'utilitza per incloure el contingut d'un fitxer Sass dins d'un altre. Això facilita la divisió del teu codi en múltiples fitxers per a una millor organització i mantenibilitat. 

Suposa que tens dos fitxers Sass: `_variables.scss` i `styles.scss`.

Contingut de `_variables.scss`:

```scss
// _variables.scss
$color-primary: #3498db;
$font-size-heading: 24px;
```

Contingut de `styles.scss`:

```scss
// styles.scss
@import 'variables';

body {
  background-color: $color-primary;
  font-size: $font-size-heading;
}

a {
  color: $color-primary;
}
```

En aquest exemple, el fitxer `styles.scss` importa el contingut de `_variables.scss` amb la línia `@import 'variables';`. Aquesta línia indica a Sass que inclogui el contingut del fitxer `variables.scss` en el punt on es fa l'@import. Així, les variables com `$color-primary` i `$font-size-heading` es tornen disponibles al fitxer `styles.scss`.

És important notar que el fitxer amb les variables comença amb un guió baix `_` (underscore). Aquesta convenció indica que el fitxer és destinat a ser importat i no ha de ser compilat independentment.

Quan compiles el fitxer `styles.scss`, les variables definides a `_variables.scss` es fusionaran amb el contingut de `styles.scss` i es generarà un fitxer CSS únic. Per fer això, pots utilitzar la comanda següent:

```bash
sass styles.scss output.css
```

Amb aquesta estructura, pots mantenir parts específiques del teu codi en fitxers separats i utilitzar `@import` per incorporar-les als teus fitxers principals, facilitant així el manteniment i la gestió del codi.

També serveix per a importar el contingut de regles d'un arxiu dins d'un altre.

=== "reset.scss"
    ```scss
        html,
        body,
        ul,
        ol {
        margin: 0;
        padding: 0;
        }
    ```

=== "main.scss"
    ```scss
        @import "reset";

        body {
        font-family: Helvetica, sans-serif;
        font-size: 18px;
        color: red;
        }
    ```
=== "sortida main.css"
    ```scss
        html, body, ul, ol {
        margin: 0;
        padding: 0;
        }

        body {
        font-family: Helvetica, sans-serif;
        font-size: 18px;
        color: red;
        }
    ```

#### @mixin

Un `@mixin` a SCSS (Sassy CSS) és una manera de reunir un conjunt de declaracions CSS reutilitzables que poden ser incloses en altres regles o selectores. S'afegeixen amb la paraula clau `@mixin`, seguida d'un nom i un conjunt de declaracions CSS.

Aquí tens un exemple bàsic de com podríeu definir un `@mixin` a SCSS:

```scss
@mixin text-en-negreta {
  font-weight: bold;
  color: #333;
}

body {
  @include text-en-negreta;
}

.encapçalament {
  @include text-en-negreta;
  font-size: 18px;
}
```

En aquest exemple, s'ha creat un `@mixin` anomenat `text-en-negreta` que conté les propietats `font-weight` i `color`. Aquest `@mixin` s'utilitza després a les regles `body` i `.encapçalament` amb la directiva `@include`. Això permet reutilitzar fàcilment les mateixes propietats en diferents parts del teu codi SCSS.

Quan es compila el codi SCSS a CSS, les regles `body` i `.encapçalament` contindran les propietats definides al `@mixin` `text-en-negreta`.

Els `@mixin` són útils per evitar la repetició de codi i facilitar el manteniment en actualitzar estils comuns en diversos llocs. A més, pots passar arguments als `@mixin` per fer-los més flexibles i personalitzables.

#### @extend

A SCSS (Sassy CSS), `@extend` és una característica que permet a un selector heretar tots els estils d'un altre selector. En altres paraules, permet que un selector comparteixi les regles de CSS amb un altre selector, afegint-les al seu propi conjunt de regles.

Aquí tens un exemple simple de com utilitzar `@extend` a SCSS:

```scss
// Definició d'un estil que volem reutilitzar
.estil-compartit {
  font-weight: bold;
  color: blue;
}

// Utilitzant @extend per heretar l'estil
.element1 {
  @extend .estil-compartit;
  font-size: 16px;
}

.element2 {
  @extend .estil-compartit;
  text-decoration: underline;
}
```

En aquest exemple, l'estil definit a `.estil-compartit` s'aplica als selectors `.element1` i `.element2` mitjançant l'ús de `@extend`. La sortida compilada serà similar a això:

```css
.estil-compartit, .element1, .element2 {
  font-weight: bold;
  color: blue;
}

.element1 {
  font-size: 16px;
}

.element2 {
  text-decoration: underline;
}
```

L'ús de `@extend` pot ser útil per mantenir el codi més modular i evitar la repetició innecessària de codi CSS quan diversos selectors comparteixen les mateixes propietats. No obstant això, és important utilitzar-ho amb cura ja que un ús excessiu pot conduir a un codi CSS més gran del necessari i, en alguns casos, afectar el rendiment de la pàgina web.

#### Diferències entre @mixin i @extend

Les directrius `@extend` i `@mixin` són dues característiques claus de Sassy CSS (SCSS), però serveixen per propòsits diferents:

##### **`@extend`:**
   - **Propòsit:** Permet que un selector hereti tots els estils d'un altre selector.
   - **Ús:** S'aplica quan vols que diversos selectors compartixin el mateix conjunt de propietats CSS.
   - **Exemple:**
     ```scss
     .estil-compartit {
       font-weight: bold;
       color: blue;
     }

     .element1 {
       @extend .estil-compartit;
       font-size: 16px;
     }

     .element2 {
       @extend .estil-compartit;
       text-decoration: underline;
     }
     ```
   - **Sortida Compilada:**
     ```css
     .estil-compartit, .element1, .element2 {
       font-weight: bold;
       color: blue;
     }

     .element1 {
       font-size: 16px;
     }

     .element2 {
       text-decoration: underline;
     }
     ```

##### **`@mixin`:**
   - **Propòsit:** Permet definir blocs de codi CSS reutilitzables que poden ser inclosos en altres regles o selectores.
   - **Ús:** S'utilitza quan vols agrupar i reutilitzar conjunts de declaracions CSS.
   - **Exemple:**
     ```scss
     @mixin text-en-negreta {
       font-weight: bold;
       color: #333;
     }

     body {
       @include text-en-negreta;
     }

     .encapçalament {
       @include text-en-negreta;
       font-size: 18px;
     }
     ```
   - **Sortida Compilada:**
     ```css
     body {
       font-weight: bold;
       color: #333;
     }

     .encapçalament {
       font-weight: bold;
       color: #333;
       font-size: 18px;
     }
     ```

En resum, `@extend` és útil per compartir conjunts complets de propietats CSS entre selectors, mentre que `@mixin` és útil per agrupar i reutilitzar blocs de codi CSS més petits. Cada un té el seu ús específic i es pot utilitzar segons les necessitats del teu projecte.