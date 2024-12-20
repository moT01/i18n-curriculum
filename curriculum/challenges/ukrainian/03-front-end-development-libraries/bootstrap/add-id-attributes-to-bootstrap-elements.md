---
id: bad87fee1348bd9aec908853
title: Додайте атрибути id до елементів Bootstrap
challengeType: 0
forumTopicId: 16639
dashedName: add-id-attributes-to-bootstrap-elements
---

# --description--

Recall that in addition to class attributes, you can give each of your elements an `id` attribute.

Кожен id має бути унікальним для певного елементу і використовуватись лише один раз на сторінці.

Надамо унікальний id кожному елементу `div` класу `well`.

Пам’ятайте, що id можна надати ось так:

```html
<div class="well" id="center-well">
```

Надайте `well` ліворуч id зі значенням `left-well`. Надайте `well` праворуч id зі значенням `right-well`.

# --hints--

`well` ліворуч повинен мати id зі значенням `left-well`.

```js
const column = document.querySelectorAll('.col-xs-6')[0];
const leftWall = column?.querySelectorAll(`:scope ${'#left-well'}`);
assert.lengthOf(leftWall,1)
```

`well` праворуч повинен мати id зі значенням `right-well`.

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
