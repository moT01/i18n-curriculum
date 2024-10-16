---
id: 587d7db6367417b2b2512b9a
title: Haz coincidir caracteres que aparecen cero o más veces
challengeType: 1
forumTopicId: 301351
dashedName: match-characters-that-occur-zero-or-more-times
---

# --description--

The last challenge used the plus `+` sign to look for characters that occur one or more times. There's also an option that matches characters that occur zero or more times.

El carácter que hace esto es el asterisco o la estrella: `*`.

```js
let soccerWord = "gooooooooal!";
let gPhrase = "gut feeling";
let oPhrase = "over the moon";
let goRegex = /go*/;
soccerWord.match(goRegex);
gPhrase.match(goRegex);
oPhrase.match(goRegex);
```

En orden, los tres `match` devolverán los valores `["goooooooo"]`, `["g"]`, y `null`.

# --instructions--

Para este desafío, `chewieQuote` ha sido inicializada entre bastidores con la cadena `Aaaaaaaaaaaaaaaarrrgh!`. Crea una expresión regular `chewieRegex` que utilice el carácter `*` para encontrar el carácter `A` mayúscula seguido inmediatamente por cero o más caracteres `a` minúscula en `chewieQuote`. Tu expresión regular no necesita banderas o clases de caracteres, y no debe coincidir con ninguna de las otras comillas.

# --hints--

Tu expresión regular `chewieRegex` debe utilizar el `*` para que coincida con cero o más caracteres `a`.

```js
assert(/\*/.test(chewieRegex.source));
```

Tu expresión regular debe coincidir con la cadena `A` en `chewieQuote`.

```js
assert(result[0][0] === 'A');
```

Tu expresión regular debe coincidir con la cadena `Aaaaaaaaaaaaaaaa` en `chewieQuote`.

```js
assert(result[0] === 'Aaaaaaaaaaaaaaaa');
```

Tu expresión regular `chewieRegex` debe coincidir con 16 caracteres en `chewieQuote`.

```js
assert(result[0].length === 16);
```

Tu expresión regular no debe coincidir con ningún carácter con la cadena `He made a fair move. Screaming about it can't help you.`

```js
assert(
  !"He made a fair move. Screaming about it can't help you.".match(chewieRegex)
);
```

Tu expresión regular no debe coincidir con ningún carácter con la cadena `Let him have it. It's not wise to upset a Wookiee.`

```js
assert(
  !"Let him have it. It's not wise to upset a Wookiee.".match(chewieRegex)
);
```

# --seed--

## --before-user-code--

```js
const chewieQuote = "Aaaaaaaaaaaaaaaarrrgh!";
```

## --seed-contents--

```js
// Only change code below this line
let chewieRegex = /change/; // Change this line
// Only change code above this line

let result = chewieQuote.match(chewieRegex);
```

# --solutions--

```js
  let chewieRegex = /Aa*/;
  let result = chewieQuote.match(chewieRegex);
```
