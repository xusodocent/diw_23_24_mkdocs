
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
