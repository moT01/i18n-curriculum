---
id: 587d7789367417b2b2512aa4
title: Mejorar la accesibilidad del contenido de audio con el elemento de audio
challengeType: 0
videoUrl: 'https://scrimba.com/c/cVJVkcZ'
forumTopicId: 301014
dashedName: improve-accessibility-of-audio-content-with-the-audio-element
---

# --description--

El elemento `audio` de HTLM le da un significado semántico cuando contiene sonido o contenido de flujo de audio en el código. El contenido del audio también necesita un texto alternativo para que las personas sordas o con dificultad para escuchar puedan acceder al mismo. Para esto debe tener un texto cercano en la página o un enlace a una transcripción.

La etiqueta de `audio` suporta los atributos `controls`. Esto muestra los controles por defecto de reproducir, pausar, entre otros controles, y soporta la funcionalidad del teclado. Este es un atributo booleano por lo que no necesita un valor, su presencia en la etiqueta activa la configuración.

Este es un ejemplo:

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg">
  <source src="audio/meow.ogg" type="audio/ogg">
</audio>
```

**Note:** El contenido multimedia generalmente tiene componentes visuales y de audio. Se necesita sincronizar los subtítulos y una transcripción para que los usuarios con dificultades de vista o con problemas para escuchar puedan tener acceso a las mismas. Por lo general, un desarrollador de web no se responsabiliza de la creación de subtítulos o transcripciones pero necesita saber para incluirlos.

# --instructions--

Es hora de salir del Camper Cat y conocer a nuestro compañero Zersiax (@zersiax), un campeón en accesibilidad y un usuario de lector de pantalla. Para escuchar el fragmento de audio de su lector de pantalla en acción, agregue un elemento `audio` después del elemento `p`. Incluye el atributo `controls`. Luego ubica un elemento `source` dentro del `audio` etiquetado con el atributo `src` asignado a `https://cdn.freecodecamp.org/curriculum/applied-accessibility/screen-reader.mp3` y el atributo`type` asignado a `"audio/mpeg"`.

**Note:** El clip del audio puede sonar rápido y quizás sea difícil de entender pero esta velocidad es normal para los lectores de pantalla.

# --hints--

Tu código debe tener una etiqueta `audio`.

```js
assert.lengthOf(document.querySelectorAll('audio'),1);
```

El elemento `audio` debe tener una etiqueta de cierre.

```js
assert.match(code,/<audio.*>[\s\S]*<\/audio>/g);
assert.lengthOf(code.match(/<\/audio>/g),1);
```

La etiqueta `audio` debe tener el atributo `controls`.

```js
assert.exists(document.querySelector('audio')?.getAttribute('controls'));
```

Tu código debe tener una etiqueta `source`.

```js
assert.lengthOf(document.querySelectorAll('source'), 1);
```

La etiqueta `source` debe estar adentro de las etiquetas `audio`.

```js
const audio = document.querySelector('audio');
const children = audio.querySelectorAll(`:scope ${'source'}`);
assert.lengthOf(children,1);
```

El valor para el atributo `src` en `source` debe coincidir exactamente con el link en las instrucciones.

```js
assert.equal(
  document.querySelector('source')?.getAttribute('src'),
  'https://cdn.freecodecamp.org/curriculum/applied-accessibility/screen-reader.mp3'
);
```

El código debe incluir un atributo `type` en la etiqueta `source` con un valor de audio/mpeg.

```js
assert.equal(document.querySelector('source')?.getAttribute('type'), 'audio/mpeg');
```

# --seed--

## --seed-contents--

```html
<body>
  <header>
    <h1>Real Coding Ninjas</h1>
  </header>
  <main>
    <p>A sound clip of Zersiax's screen reader in action.</p>



  </main>
</body>
```

# --solutions--

```html
<body>
  <header>
    <h1>Real Coding Ninjas</h1>
  </header>
  <main>
    <p>A sound clip of Zersiax's screen reader in action.</p>
    <audio controls>
      <source src="https://cdn.freecodecamp.org/curriculum/applied-accessibility/screen-reader.mp3" type="audio/mpeg"/>
    </audio>
  </main>
</body>
```
