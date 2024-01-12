## Iniciar reproducció

Iniciar la reproducció en polsar un botó.

```html
<video id="video" width="700" height="350">  
    <source src="video.mp4">   
    <source src="video.ogv"> 
</video> 
<input type="button" id="boton" value="Reproducir"> 

<script> 
function iniciar() { 
   var boton=document.getElementById('boton'); 
   boton.addEventListener('click', presionar, false); 
} 
function presionar() { 
   var video=document.getElementById('video'); 
   video.play(); 
} 
window.addEventListener('load', iniciar, false); 
</script> 
```

