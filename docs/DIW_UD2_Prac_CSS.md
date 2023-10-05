---
title: UD2 - INTRODUCCIÓ A CSS
titlepage: true
subtitle: Xuso Ortí Monton - Josep Magraner Ramon
lang: es
toc-own-page: true
toc-title: Continguts
titlepage-rule-height: 0
titlepage-text-color: "7421D6"
titlepage-background: "./img/portades2024DAW.png"
page-background: "./img/bkaztar.png"
header-left: \includegraphics{./img/logocap.png} 2daw i 2daw_semi
header-right: Curs 2023-2024
footer-left: IES Jaume II el Just - Disseny d'interfícies web 
footer-right: \thepage/\pageref{LastPage}
header-includes:
    - \usepackage{graphicx}
    - \usepackage{lastpage}
    - \usepackage{xltxtra}
    - \usepackage{listings}
    - \usepackage{pdflscape}
    - \usepackage{caption}
...

## Maquetació web

Partint dels arxius que es proporcionen a la plataforma, confecciona el `CSS` per tal d'obtindre un resultat com el següent:

![Resultat a obtindre](img/resultat_prac.jpg)

L'estructura de la pàgina serà pràcticament igual a la de l'exercici anterior, la podeu veure en el fitxer **index.HTML**, tindrem un `<div id="page">` que serà el contenidor de tota la pàgina, i dins d'aquest, tindrem els següents
elements:

-   Un `<div id="header">` que contindrà un `<h1>` amb el títol de la pàgina.
-   Un `<div id="nav">` que contindrà una llista desordenada amb els enllaços del
menú de navegació.
-   Un <*div id="*content"> que contindrà tres `<div class="article">`.
Cada `<div class="article">` contindrà un `<div class="article_header">` que, al seu torn, contindrà una imatge i un `<h2>` amb el títol de l'article. El `<div class="article">` també contindrà un parell de paràgrafs de text. Després del `<div id="content">` tenim un `<div id="footer">` amb el peu de pàgina que contindrà un paràgraf de text.

Si visualitzeu el fitxer **index.html** en el vostre navegador, observareu que la pàgina
no apareix com es mostra en la imatge. Això és perquè el fitxer **estils.css** de la carpeta *css està buit. El que heu de fer en aquest exercici és completar els estils necessaris perquè la pàgina es mostre com s'espera.

A continuació, veurem els estils que hem de crear:

-   Utilitzant el selector universal, configurarem a *0px el marge intern i
extern de tots els elements.

Element `<body>`:

-   Marge intern superior 20px.
-   Text alineat al centre.
-   Imatge de fons "../imgs/old_map.png". Per a canviar la imatge de fons d'un element, utilitzarem la propietat `background-image`.

Com el fitxer d'estils està en la carpeta *css i les imatges en la carpeta *imgs, haurem d'indicar la ruta relativa des del lloc on estan els estils fins al lloc on estan les imatges, en
aquest cas "../imgs/old_map.png". Quan indiquem la ruta d'unrecurs en un fitxer d'estils, hem d'utilitzar la funció *url, per tant, per a canviar la imatge de fons, farem el següent:
`background-image: url("../imgs/old_map.png");`

Element `page`:

-   Tindrà un ample de *960px.
-   Els marges superior i inferior seran de *0px, mentre que l'esquerre i dret seran automàtics.
-   El text estarà alineat a l'esquerra.
  
Element `header`:

-   La font *Courier de color blanc i grandària 1em2.
-   La vora inferior tindrà 6px, serà negre i d'estil sòlid.
-   El color de fons serà #313B44.
  
Si observem la capçalera de la pàgina, al costat del títol de la mateixa apareix una imatge amb els logos de `html`, `CSS` i `javascript`.

Veiem que en l'arxiu **index.html** no tenim cap element `<img>`, així que, podem deduir que aquesta imatge es troba en els estils de la pàgina. En general, quan una imatge té més relació amb l'aspecte visual de la pàgina que amb els continguts d'aquesta, la introduirem sempre per mitjà dels estils.

Vegem com hem de configurar els estils de l'element `<h1>` per a aconseguir aquesta aparença:

-   La imatge de fons serà "../imgs/logo.png".
-   Per defecte, quan col·loquem una imatge de fons xicoteta en un element més gran, la imatge es repetirà en mosaic fins a emplenar tot l'element. Per a controlar aquest comportament disposem de la propietat `background-repeat`. Com en aquest cas ens interessa que la imatge no es repetisca, assignarem el valor `no-repeat`. Per a més informació sobre aquesta propietat, podeu
consultar la [w3school](http://www.w3schools.com/cssref/pr_background-repeat.asp).
-   Quan una imatge de fons no es repeteix, podem indicar en quina posició volem que aparega utilitzant la propietat `background-position`. En aquest cas, ens interessa que aparega desplaçada 25px a l'esquerra i centrada verticalment, per tant, indicarem els següents valors: `background-position: 25px center;`. Per a més informació sobre aquesta propietat, podeu consultar
la [w3school](http://www.w3schools.com/cssref/pr_background-position.asp).
  
!!! warning "Problema amb els píxels"

        Quan utilitzem grandàries de fonts indicats en píxels ens trobem amb un problema: les
        versions d'Internet Explorer anteriors a la 9 no redimensionaran les fonts quan s'utilitza el zoom en el navegador (Ctrl +). Per a evitar aquest problema, W3C recomana l'ús de la unitat de mesura em. 1em és igual a la grandària de font actual. La grandària de font per defecte en els navegadors és de 16px, per tant, 1em serà igual a 16px. Per a convertir els *em a píxels utilitzarem la següent fórmula: em=píxels/16


Si observem la pàgina en aquest moment, veurem que el text de l'element `<h1>` es col·loca sobre la imatge de fons, la qual cosa, no és molt apropiat. Per a solucionar aquest problema, li posarem uns marges interns superior i inferior de 20px i uns marges
interns esquerre i dret de 100px.

Element `nav`:

-   La font serà `courier` de grandària 1.4em i color silver.
-   El text estarà alineat al centre.
-   La imatge de fons serà una textura que es repetirà fins a emplenar tot l'element: "../imgs/red015.jpg".
  
Vegem ara com canviarem la llista d'enllaços que es troba dins de l'element *nav perquè prenga l'aspecte que ens interessa:

-   Per als elements `<li>` de la llista desordenada tindrem una part comuna per a tots ells i una altra individual, ja que, cada opció de menú té una imatge diferent. Per aquest motiu, hem posat un id a cadascun d'ells. Vegem, en primer lloc, els estils comuns que tenen els `<li>` que estan dins del `nav`:
-   Necessitem tindre espai suficient perquè ens càpien les imatges de cadascun dels enllaços, per tant, li posarem un marge intern superior de 80px.
-   Els marges externs els configurarem de la següent forma: superior 0px, dret 100px, inferior 20px i esquerre 100px.
-   Eliminarem el `bullet` o vinyeta que col·loca el navegador per defecte en les llistes.
-   Els col·locarem en posició horitzontal convertint-los en elements `inline-block`.
-   El text estarà centrat.

!!! note "Inline o Block"

        Un element de tipus `inline-block` (`display: inline-block`) es comporta com si fora de bloc, però respecte als elements que l'envolten és un element en línia, la qual cosa permet, per exemple, establir-li uns marges interns i/o externs.

-   Col·locarem el cursor per defecte perquè quan situem el ratolí sobre l'element sense enllaç aparega el cursor adequat.
-   En cadascun dels elements <li> hem de col·locar la imatge adequada, per a això, utilitzarem els identificadors dels mateixos per a seleccionar-los:

Element `continguts`:

-   Imatge "../imgs/book.png", eliminar repetició i posició centrada horitzontalment i a 10px de la vora superior.
  
Element `vídeos`:

-   Imatge "../imgs/film.png", eliminar repetició i posició centrada horitzontalment i a 10px de la vora superior.

Element `contacte`:

-   Imatge "../imgs/mail.png", eliminar repetició i posició centrada horitzontalment i a 10px de la vora superior.

Per als enllaços:

-   Eliminarem el subratllat.
-   Color de la font `orange`.
-   Color de la font quan el ratolí està sobre ells *white.

Element `content`:

-   Font verdana de grandària 0.8em.
-   Imatge de fons "../imgs/lgrey008.jpg".

Elements de la classe article:

-   Ample de 240px.
-   Vora de 1px color lightgray i estil sòlid.
-   Color de fons white.
-   Text alineat al centre.
-   Alt de línia de 1.8em (propietat `line-height`).
-   Els marges interns els configurarem de la següent forma: esquerre, dret i superior 5px, inferior 22px.
-   Els marges externs seran de 30px.
-   Els elements d'aquesta classe han de col·locar-se un al costat de l'altre, per tant, indicarem que suren a l'esquerra. Si observem la pàgina després de posar els elements article flotants, veiem que ha desaparegut la textura de l'element *content. És com si aquest element haguera passat a tindre un alt de 0px. Això ocorre perquè, en contindre només elements flotants, l'element content pensa que està buit. Anteriorment, per a solucionar aquest problema, bastava
amb posar els estils `overflow: hidden`; i `height: 1%;` a l'element `content`. Per a més informació podeu consultar el [següent enllaç](http://librosweb.es/css_avanzado/capitulo_1/limpiar_floats.html). Però, en realitzar algunes proves amb Internet Explorer 11 m'he
trobat amb alguns problemes, així que utilitzarem la solució que es proposa en la [següent enllaç](http://www.sitepoint.com/clearing-floats-overview-different-clearfix-methods/). En concret, el que farem serà construir els estils de l'element `content` de la següent forma:

``` css
`.clearfix:before`,
.clearfix:after,
#content
{
…
width:100%;
display: *table;
}
```
Amb això, el netejat de `floats` funcionarà en tots els navegadors moderns.

Elements de la classe `article_header`:

-   Vora inferior de 1px sòlid i color #999999.

Elements `<h2>`:

-   Marges interns 10px.
-   Grandària de font 1.2em.

Element `footer`:

-   Haurà de col·locar-se davall dels elements flotants.
-   Font de color white i grandària 0.7em.
-   Text alineat al centre.
-   Color de fons #313B44.
-   Vora superior de 6px color black i sòlid.
-   Marges interns superior i inferior de 15px.

Enllaços que es troben dins de l'element `footer`:
-   Color de font blanc.
  
Amb això hauríem acabat l'exercici i hauria de visualitzar-se la pàgina web tal com apareix en la imatge.
