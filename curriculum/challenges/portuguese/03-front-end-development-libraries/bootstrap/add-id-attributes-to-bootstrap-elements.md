---
id: bad87fee1348bd9aec908853
title: Adicionar atributos id aos elementos do Bootstrap
challengeType: 0
forumTopicId: 16639
dashedName: add-id-attributes-to-bootstrap-elements
---

# --description--

Recall that in addition to class attributes, you can give each of your elements an `id` attribute.

Cada id precisa ser único para um elemento específico e utilizado apenas uma vez por página.

Vamos dar um id único para cada um de nossos elementos `div` com classe `well`.

Lembre-se de que você pode dar um id a um elemento dessa forma:

```html
<div class="well" id="center-well">
```

Dê ao poço à esquerda o id `left-well`. Dê ao poço à direita o id `right-well`.

# --hints--

O `well` da esquerda deve ter o id `left-well`.

```js
const column = document.querySelectorAll('.col-xs-6')[0];
const leftWall = column?.querySelectorAll(`:scope ${'#left-well'}`);
assert.lengthOf(leftWall,1)
```

O `well` da direita deve ter o id `right-well`.

```js
const column = document.querySelectorAll('.col-xs-6')[1];
const rightWall = column?.querySelectorAll(`:scope ${'#right-well'}`);
assert.lengthOf(rightWall,1)
```

# --seed--

## --seed-contents--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
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
      <div class="well" id="left-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well" id="right-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
  </div>
</div>
```
