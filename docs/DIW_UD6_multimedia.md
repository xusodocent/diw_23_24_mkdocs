## Video

### Formats i ús

HTML5 ofereix suport per diversos formats de vídeo. Els principals formats de vídeo compatibles amb l'element `<video>` en HTML5 són:

1. **MP4 (H.264):** És el format de vídeo més comú i ampliament suportat. Molts navegadors moderns, com Chrome, Firefox, Safari i Edge, admeten vídeos MP4 amb el códec de vídeo H.264.

   Exemple d'ús:
   ```html
   <video controls>
     <source src="video.mp4" type="video/mp4">
     Your browser does not support the video tag.
   </video>
   ```

2. **WebM (VP8 o VP9):** WebM és un format de vídeo de codi obert desenvolupat per Google. Utilitza els códecs de vídeo VP8 o VP9. Navegadors com Chrome, Firefox i Opera tenen suport per WebM.

   Exemple d'ús:
   ```html
   <video controls>
     <source src="video.webm" type="video/webm">
     Your browser does not support the video tag.
   </video>
   ```

3. **Ogg (Theora):** Ogg és un format multimèdia lliure i obert que utilitza el códec de vídeo Theora. Tot i que és menys comú que MP4 i WebM, alguns navegadors, com Firefox, admeten Ogg.

   Exemple d'ús:
   ```html
   <video controls>
     <source src="video.ogv" type="video/ogg">
     Your browser does not support the video tag.
   </video>
   ```

Al posar diversos formats de vídeo com a fonts (`<source>`), s'ofereix una solució de reserva per garantir la compatibilitat amb diversos navegadors. El navegador seleccionarà la primera font compatible amb el format de vídeo que sigui capaç de reproduir.

### Conversió

Per convertir i optimititzar vídeos, pots fer servir diferents eines i tècniques en funció de les teves necessitats i de l'entorn en què estiguis treballant. Aquí tens algunes opcions comunes:

#### 1. **Utilitzar eines de línia de comandes: FFmpeg**

[FFmpeg](https://www.ffmpeg.org/) és una potent eina de línia de comandes per convertir, optimititzar i manipular vídeos. Pots instal·lar FFmpeg al teu sistema i utilitzar-ho amb comandes com les següents:

- Convertir de MP4 a WebM:
  ```bash
  ffmpeg -i input.mp4 -c:v libvpx -c:a libvorbis output.webm
  ```

- Reduir la resolució:
  ```bash
  ffmpeg -i input.mp4 -vf "scale=640:480" -c:a copy output.mp4
  ```

#### 2. **Utilitzar eines gràfiques: HandBrake**

[HandBrake](https://handbrake.fr/) és una eina amb interfície gràfica que simplifica la conversió i optimitització de vídeos. Proporciona diverses preconfiguracions i permet personalitzar molts paràmetres.

#### 3. **Optimitzar amb servidors o serveis en línia:**

Hi ha diversos serveis en línia que ofereixen la possibilitat de pujar vídeos i obtenir-ne versions optimitzades. Exemples inclouen [Cloudinary](https://cloudinary.com/), [Zencoder](https://app.zencoder.com/), i [HandBrake's Online Video Converter](https://handbrake.fr/docs/en/1.2.0/introduction/web-optimize.html).

#### 4. **Comprimir amb paràmetres específics:**

Pots utilitzar eines com [MP4Box](https://gpac.wp.imt.fr/mp4box/) o [MKVToolNix](https://mkvtoolnix.download/) per ajustar paràmetres com la velocitat de bits, que pot afectar la qualitat i el tamany del vídeo.

#### 5. **Utilitzar serveis en línia per la conversió de format:**

Serveis com [Online-Convert](https://www.online-convert.com/) permeten pujar un vídeo i convertir-lo a diversos formats. Aquests serveis solen oferir opcions d'optimització.

Sigues conscient de les llicències i els termes d'ús quan utilitzis eines i serveis, i assegura't que estàs complint amb les normatives de drets d'autor. Optimitzar un vídeo pot comportar una pèrdua de qualitat, així que ajusta els paràmetres segons les teves necessitats específiques.

### Element `<video>` en `html5`

L'element `<video>` en HTML5 és un element integrat per reproduir vídeos dins d'una pàgina web. Aquest element proporciona una interfície nativa per reproduir vídeos sense necessitat de plugins externs. Aquí tens una descripció més detallada de l'element `<video>`:

#### Atributs Importants:

1. **`src`:** Indica la URL del fitxer de vídeo que es vol reproduir. Pot ser una URL absoluta o relativa.

   Exemple:
   ```html
   <video src="video.mp4" controls></video>
   ```

2. **`controls`:** Afegeix una barra de controls per permetre a l'usuari reproduir, pausar i ajustar el volum del vídeo.

   Exemple:
   ```html
   <video src="video.mp4" controls></video>
   ```

3. **`width` i `height`:** Defineixen l'amplada i l'altura del reproductor de vídeo. És millor utilitzar aquest atribut per ajustar les dimensions en lloc de fer-ho directament al fitxer de vídeo.

   Exemple:
   ```html
   <video src="video.mp4" width="640" height="360" controls></video>
   ```

4. **`autoplay`:** Inicia la reproducció del vídeo automàticament quan la pàgina es carrega.

   Exemple:
   ```html
   <video src="video.mp4" autoplay></video>
   ```

5. **`loop`:** Indica que el vídeo ha de reproduir-se en bucle.

   Exemple:
   ```html
   <video src="video.mp4" loop></video>
   ```

6. **`poster`:** Especifica una imatge que es mostrarà mentre el vídeo es descarrega o fins que es fa clic per reproduir-lo.

   Exemple:
   ```html
   <video src="video.mp4" poster="cover.jpg" controls></video>
   ```

#### Formats Suportats:

Els navegadors poden tenir suport per diferents formats de vídeo. Per a una compatibilitat més àmplia, pots proporcionar diverses fonts de vídeo mitjançant l'element `<source>`. Exemple:

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```

#### Mètodes JavaScript:

Pots interactuar amb l'element `<video>` des de JavaScript mitjançant mètodes com `play()`, `pause()`, i propietats com `currentTime` per controlar la reproducció del vídeo de manera programàtica.

Exemple:
```javascript
let video = document.querySelector('video');
video.play(); // Inicia la reproducció
```

#### Esdeveniments JavaScript:

L'element `<video>` també genera esdeveniments que pots gestionar mitjançant JavaScript. Alguns exemples d'esdeveniments són `play`, `pause`, `ended`, etc.

Exemple:
```javascript
video.addEventListener('ended', () => {
  console.log('Vídeo finalitzat');
});
```

En resum, l'element `<video>` és fonamental per incorporar contingut multimèdia als llocs web de manera nativa amb HTML5, proporcionant control directe i interacció amb els usuaris.

## Audio

### Formats

Els principals formats d'arxius d'àudio són diversos i varien en funció de les necessitats i de la finalitat d'ús. Aquí tens alguns dels formats d'arxius d'àudio més comuns:

1. **MP3 (MPEG Audio Layer III):** És un dels formats d'arxius d'àudio més populars i àmpliament utilitzats. Ofereix una bona qualitat de so amb una compressió de dades significativa, la qual cosa el fa adequat per a la transmissió en línia i l'emmagatzematge d'àudio.

2. **AAC (Advanced Audio Coding):** És un format d'arxiu d'àudio amb pèrdua de qualitat utilitzat àmpliament en plataformes com iTunes. Ofereix una qualitat de so superior a la de l'MP3 amb mides de fitxers comparables o més petites.

3. **WAV (Waveform Audio File Format):** És un format d'arxiu d'àudio sense compressió, el que significa que ofereix una qualitat de so excel·lent, però els fitxers poden ser molt grans. És comú utilitzar WAV per a l'emmagatzematge de so d'alta qualitat sense compressió.

4. **FLAC (Free Lossless Audio Codec):** És un format sense pèrdua que manté la qualitat del so original sense comprimir tant com WAV. És popular entre els audiòfils per la seva capacitat de mantenir la qualitat d'àudio sense augmentar excessivament les mides dels fitxers.

5. **Ogg Vorbis:** És un format d'arxiu d'àudio amb compressió de pèrdua. És similar a l'MP3, però sense les restriccions de patent. És utilitzat freqüentment en aplicacions de codi obert i lliure.

6. **AIFF (Audio Interchange File Format):** És un format d'arxiu sense compressió desenvolupat per Apple. Com el WAV, manté la qualitat del so original, però els fitxers poden ser relativament grans.

7. **M4A:** És un format d'arxiu d'àudio utilitzat com a contenidor per a la compressió AAC. És comú a l'ecosistema d'Apple i es pot trobar en iTunes.

8. **WMA (Windows Media Audio):** És un format d'arxiu d'àudio desenvolupat per Microsoft. Ofereix compressió amb pèrdua i sense pèrdua, i es solia utilitzar àmpliament en el passat.

La elecció del format d'arxiu d'àudio dependrà de diversos factors, incloent la qualitat desitjada, els requisits d'emmagatzematge, la compatibilitat amb dispositius i plataformes específiques, i altres necessitats específiques del projecte.

### Ús

L'element `<audio>` en HTML5 és una etiqueta utilitzada per incrustar arxius d'àudio en pàgines web. Aquest element permet als desenvolupadors reproduir contingut d'àudio directament a la pàgina sense necessitat de plugins externs. Aquí tens una descripció més detallada de l'element `<audio>`:

#### Atributs Importants:

1. **`src`:** Indica la URL del fitxer d'àudio que es vol reproduir. Pot ser una URL absoluta o relativa.

   Exemple:
   ```html
   <audio src="audio.mp3" controls></audio>
   ```

2. **`controls`:** Afegeix una barra de controls per permetre a l'usuari reproduir, pausar i ajustar el volum del contingut d'àudio.

   Exemple:
   ```html
   <audio src="audio.mp3" controls></audio>
   ```

3. **`autoplay`:** Inicia la reproducció del contingut d'àudio automàticament quan la pàgina es carrega.

   Exemple:
   ```html
   <audio src="audio.mp3" autoplay></audio>
   ```

4. **`loop`:** Indica que l'àudio ha de reproduir-se en bucle.

   Exemple:
   ```html
   <audio src="audio.mp3" loop></audio>
   ```

5. **`preload`:** Especifica com el navegador ha de carregar el fitxer d'àudio. Pot ser `none`, `metadata`, o `auto`.

   Exemple:
   ```html
   <audio src="audio.mp3" preload="auto"></audio>
   ```

#### Formats Suportats:

Els navegadors poden tenir suport per diferents formats d'àudio. Com amb l'element `<video>`, pots proporcionar diverses fonts d'àudio amb l'element `<source>` per garantir una millor compatibilitat.

Exemple:
```html
<audio controls>
  <source src="audio.mp3" type="audio/mp3">
  <source src="audio.ogg" type="audio/ogg">
  Your browser does not support the audio tag.
</audio>
```

#### Mètodes JavaScript:

Pots interactuar amb l'element `<audio>` des de JavaScript mitjançant mètodes com `play()`, `pause()`, i propietats com `currentTime` per controlar la reproducció de l'àudio de manera programàtica.

Exemple:
```javascript
let audio = document.querySelector('audio');
audio.play(); // Inicia la reproducció
```

#### Esdeveniments JavaScript:

L'element `<audio>` també genera esdeveniments que pots gestionar mitjançant JavaScript. Alguns exemples d'esdeveniments són `play`, `pause`, `ended`, etc.

Exemple:
```javascript
audio.addEventListener('ended', () => {
  console.log('Àudio finalitzat');
});
```

#### Accessibilitat:

L'element `<audio>` també ofereix suport a etiquetes d'accessibilitat com `alt` i `aria-*` per proporcionar una millor experiència per als usuaris amb necessitats especials.

```html
<audio src="audio.mp3" controls aria-label="Reproductor d'àudio"></audio>
```

L'element `<audio>` és essencial per a la incorporació d'àudio a les pàgines web i permet als desenvolupadors oferir una experiència de mitjans rica sense recórrer a plugins externs.

### Optimitar audio per a la web

Optimitzar i convertir arxius d'àudio per a la web implica trobar un equilibri entre la qualitat del so i la grandària del fitxer. A continuació, t'indico alguns passos generals i eines que pots utilitzar per a aquest propòsit:

#### 1. **Comprimir l'àudio:**

La compressió d'àudio redueix la grandària del fitxer sense una pèrdua significativa de qualitat perceptible. Aquí tens algunes eines que pots utilitzar:

- **[Audacity](https://www.audacityteam.org/):** Audacity és un editor d'àudio de codi obert que permet exportar els fitxers amb diferents opcions de compressió.

- **[FFmpeg](https://www.ffmpeg.org/):** Pots utilitzar FFmpeg amb diferents paràmetres per comprimir i convertir arxius d'àudio. Per exemple, per convertir un fitxer a MP3 amb una baixa velocitat de bits:

  ```bash
  ffmpeg -i input.wav -b:a 96k output.mp3
  ```

#### 2. **Utilitzar formats amb compressió:**

Opta per formats d'àudio amb compressió eficient com MP3 o AAC. Aquests formats ofereixen una bona qualitat de so amb mides de fitxer relativament petites.

#### 3. **Ajustar la qualitat:**

En molts casos, pots reduir la qualitat de l'àudio lleugerament sense que això sigui perceptible per l'usuari mitjà. Ajusta la velocitat de bits i altres paràmetres segons les teves necessitats.

### 4. **Utilitzar codecs eficients:**

Els códecs de compressió com Ogg Vorbis o Opus poden proporcionar una bona qualitat de so amb mides de fitxer reduïdes. Assegura't que els teus fitxers d'àudio utilitzen códecs eficients.

#### 5. **Optimitzar la compatibilitat del navegador:**

Considera oferir diverses fonts d'àudio mitjançant l'element `<source>` per garantir la compatibilitat amb diferents navegadors. Exemple:

```html
<audio controls>
  <source src="audio.mp3" type="audio/mp3">
  <source src="audio.ogg" type="audio/ogg">
  Your browser does not support the audio tag.
</audio>
```

#### 6. **Utilitzar eines en línia:**

Hi ha diverses eines en línia que poden ajudar-te a comprimir i optimitzar arxius d'àudio, com [Online Audio Converter](https://online-audio-converter.com/), [Convertio](https://convertio.co/audio-converter/), entre d'altres.

#### 7. **Cache i CDN:**

Utilitza serveis de Content Delivery Network (CDN) per optimitzar la distribució dels teus arxius d'àudio. També pots aprofitar les polítiques de cache per millorar la càrrega de la pàgina.

Optimitzar arxius d'àudio és una part important de l'optimització web general. Prova diferents configuracions i mides de fitxers per trobar el millor equilibri entre qualitat i grandària del fitxer per a les necessitats específiques del teu lloc web.

## Canvas

Clar, aquí tens un senzill tutorial per començar a utilitzar l'element `<canvas>` en HTML5. L'element `<canvas>` permet dibuixar gràfics, animacions i d'altres elements visuals en una pàgina web.

### Pas 1: Crear l'estructura HTML

```html
<!DOCTYPE html>
<html lang="ca">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Canvas Tutorial</title>
  <style>
    canvas {
      border: 1px solid #000;
    }
  </style>
</head>
<body>
  <canvas id="myCanvas" width="400" height="200"></canvas>

  <script>
    // Aquí anirà el teu codi JavaScript per gestionar el canvas
  </script>
</body>
</html>
```

### Pas 2: Accedir al Canvas des de JavaScript

Utilitza JavaScript per obtenir el context del canvas. El context determina si estàs treballant amb gràfics 2D o 3D. Per ara, ens centrarem en 2D.

```javascript
const canvas = document.getElementById('myCanvas');
const context = canvas.getContext('2d');
```

### Pas 3: Dibuixar formes bàsiques

#### Dibuixar un rectangle:

```javascript
context.fillStyle = 'blue'; // Color de ple per al rectangle
context.fillRect(50, 50, 100, 80); // Posició x, y i dimensions width, height
```

#### Dibuixar un cercle:

```javascript
context.fillStyle = 'red'; // Color de ple per al cercle
context.beginPath();
context.arc(200, 100, 30, 0, 2 * Math.PI); // Posició x, y, radi, angle inicial, angle final
context.fill();
```

### Pas 4: Afegir text al Canvas

```javascript
context.font = '20px Arial'; // Estil de la font
context.fillStyle = 'black'; // Color del text
context.fillText('Hello, Canvas!', 50, 180); // Text i posició x, y
```

### Pas 5: Gestió d'events (Exemple: Mous)

Afegir un event listener per detectar clics de ratolí:

```javascript
canvas.addEventListener('click', (event) => {
  const mouseX = event.clientX - canvas.getBoundingClientRect().left;
  const mouseY = event.clientY - canvas.getBoundingClientRect().top;

  // Aquí pots fer quelcom amb les coordenades del clic del ratolí
  console.log(`Clic a les coordenades: (${mouseX}, ${mouseY})`);
});
```

Aquest és un tutorial bàsic que et proporciona una introducció a l'ús de l'element `<canvas>` en HTML5. A mesura que et familiaritzis amb aquest concepte, podràs explorar animacions, transformacions i altres funcionalitats més avançades. Pots trobar més informació i exemples a la [documentació MDN sobre l'element `<canvas>`](https://developer.mozilla.org/ca/docs/Web/HTML/Element/canvas).

## Animacions

Per fer animacions en HTML5 utilitzant keyframes i la propietat `animation` de CSS, pots seguir aquest exemple senzill. En aquest cas, crearem una animació que fa que un element es mogui de dreta a esquerra.

### 1. Estructura HTML bàsica

```html
<!DOCTYPE html>
<html lang="ca">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animació amb Keyframes i la Propietat Animation</title>
  <style>
    @keyframes moureEsquerraDreta {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(300px);
      }
    }

    .caixa {
      width: 50px;
      height: 50px;
      background-color: #3498db;
      position: relative;
      animation: moureEsquerraDreta 2s linear infinite; /* Nom de l'animació, durada, tipus de temporització, iteracions (infinite per repetir indefinidament) */
    }
  </style>
</head>
<body>
  <div class="caixa"></div>
</body>
</html>
```

### 2. Explicació del Codi

- **`@keyframes moureEsquerraDreta`:** Defineix l'animació mitjançant keyframes. En aquest cas, l'animació es diu "moureEsquerraDreta". Utilitzem dos estats clau (0% i 100%) per indicar l'estat inicial i final de l'animació. En aquest exemple, estem fent que la caixa es mogui 300 píxels cap a la dreta.

- **`.caixa`:** És un div amb la classe "caixa" al qual li aplicarem l'animació. Establim la mida i el color de fons, i indiquem que volem que l'animació "moureEsquerraDreta" duri 2 segons, sigui lineal i es repeteixi infinitament.

### 3. Personalització

Pots personalitzar l'animació canviant les propietats com la durada, el tipus de temporització, la iteració i les propietats CSS que canvien durant l'animació. Pots afegir més keyframes si vols més etapes d'animació.

### 4. Afegir més animacions

Pots afegir més animacions canviant les propietats dels keyframes i afegint nous selectors CSS amb diferents classes.

Aquest és un exemple senzill que demostra com utilitzar keyframes i la propietat `animation` de CSS per crear animacions en HTML5. Pots experimentar i adaptar aquesta base per crear animacions més complexes i personalitzades.

!!! note "Exemples"

    Tens exemples d'algunes animacions en [aquesta web](https://www.eniun.com/animaciones-keyframes-animation/). També tens [aquestes animacions més completes](https://webdesign.tutsplus.com/es/15-inspiring-examples-of-css-animation-on-codepen--cms-23937a).

