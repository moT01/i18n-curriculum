---
id: bad87fee1348bd9aec908849
title: Adicionar elementos aos poços no Bootstrap
challengeType: 0
forumTopicId: 16636
dashedName: add-elements-within-your-bootstrap-wells
---

# --description--

Now we're several `div` elements deep on each column of our row. This is as deep as we'll need to go. Now we can add our `button` elements.

Aninhe três elementos `button` dentro de cada um dos elementos `div` contendo o nome de classe `well`.

# --hints--

Três elementos `button` devem ser aninhados dentro de cada um dos elementos `div` com a classe `well`.

```js
const buttonOne = document.querySelectorAll('div.well')?.[0];
const buttonOneChildren = buttonOne?.querySelectorAll(`:scope ${'button'}`);
assert.lengthOf(buttonOneChildren,3);

const buttonTwo = document.querySelectorAll('div.well')?.[1]
const buttonTwoChildren = buttonTwo?.querySelectorAll(`:scope ${'button'}`);
assert.lengthOf(buttonTwoChildren,3);
```

Você deve ter o total de 6 elementos `button`.

```js
assert.lengthOf(document.querySelectorAll('button'), 6);
```

Todos os elementos `button` devem ter tags de fechamento.

```js
assert.match(code,/<\/button>/g);
assert.match(code,/<button/g);
assert.equal(code.match(/<\/button>/g).length,code.match(/<button/g).length);
```

# --seed--

## --seed-contents--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">



      </div>
    </div>
  </div>
</div>
```

# --solutions--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button></button>
        <button></button>
        <button></button>
      </div>
    </div>
  </div>
</div>
```
