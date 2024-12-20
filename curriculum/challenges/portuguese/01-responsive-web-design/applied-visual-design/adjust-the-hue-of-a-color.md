---
id: 587d78a4367417b2b2512ad4
title: Ajustar a tonalidade de uma cor
challengeType: 0
videoUrl: 'https://scrimba.com/c/cPp38TZ'
forumTopicId: 301036
dashedName: adjust-the-hue-of-a-color
---

# --description--

Colors have several characteristics including hue, saturation, and lightness. CSS3 introduced the `hsl()` function as an alternative way to pick a color by directly stating these characteristics.

**Tonalidade** é o que as pessoas geralmente chamam de 'cor'. Se você imaginar um espectro de cores começando com o vermelho à esquerda, passando pelo verde no meio e pelo azul à direita, a tonalidade é qualquer cor que esteja dentro deste espectro. No `hsl()`, a tonalidade é definida usando o conceito de círculo cromático em vez de um espectro, onde o ângulo da cor no círculo é um valor entre 0 e 360.

**Saturação** é a quantidade de cinza em uma cor. Uma cor totalmente saturada não contém cinza e uma cor minimamente saturada é quase totalmente cinza. Essa característica é definida usando porcentagem, onde 100% é totalmente saturado.

**Luminosidade** é a quantidade de branco ou preto em uma cor. Um valor válido, em porcentagem, varia de 0% (preto) a 100% (branco), onde 50% é a cor normal.

Aqui estão alguns exemplos de uso do `hsl()` com cores totalmente saturadas e luminosidade normal:

<table><thead><tr><th>Color</th><th>HSL</th></tr></thead><tbody><tr><td>red</td><td>hsl(0, 100%, 50%)</td></tr><tr><td>yellow</td><td>hsl(60, 100%, 50%)</td></tr><tr><td>green</td><td>hsl(120, 100%, 50%)</td></tr><tr><td>cyan</td><td>hsl(180, 100%, 50%)</td></tr><tr><td>blue</td><td>hsl(240, 100%, 50%)</td></tr><tr><td>magenta</td><td>hsl(300, 100%, 50%)</td></tr></tbody></table>

# --instructions--

Altere a propriedade `background-color` de cada elemento `div` com base nos nomes das classes (`green`, `cyan` ou `blue`) usando `hsl()`. Todos as três devem estar totalmente saturadas e ter luminosidade normal.

# --hints--

Você deve usar a função `hsl()` para declarar a cor verde.

```js
assert.match(code,/\.green\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

Você deve usar a função `hsl()` para declarar a cor ciano.

```js
assert.match(code,/\.cyan\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

Você deve usar a função `hsl()` para declarar a cor azul.

```js
assert.match(code,/\.blue\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

O elemento `div` com a classe `green` deve ter apropriedade `background-color` com o valor green (verde).

```js
const greenElement = document.querySelector(".green");
const greenStyle = window.getComputedStyle(greenElement); 
assert.equal(greenStyle?.backgroundColor, 'rgb(0, 255, 0)');
```

O elemento `div` com a classe `cyan` deve ter a propriedade `background-color` com o valor cyan (ciano).

```js
const cyanElement = document.querySelector(".cyan");
const cyanStyle = window.getComputedStyle(cyanElement); 
assert.equal(cyanStyle?.backgroundColor, 'rgb(0, 255, 255)');
```

O elemento `div` com a classe `blue` deve ter a propriedade `background-color` com o valor blue (azul).

```js
const blueElement = document.querySelector(".blue");
const blueStyle = window.getComputedStyle(blueElement); 
assert.equal(blueStyle?.backgroundColor, 'rgb(0, 0, 255)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: #FFFFFF;
  }

  .green {
    background-color: #000000;
  }

  .cyan {
    background-color: #000000;
  }

  .blue {
    background-color: #000000;
  }

  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>

<div class="green"></div>
<div class="cyan"></div>
<div class="blue"></div>
```

# --solutions--

```html
<style>
  body {
    background-color: #FFFFFF;
  }

  .green {
    background-color: hsl(120, 100%, 50%);
  }

  .cyan {
    background-color:   hsl(180, 100%, 50%);
  }

  .blue {
    background-color: hsl(240, 100%, 50%);
  }

  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>
<div class="green"></div>
<div class="cyan"></div>
<div class="blue"></div>
```
