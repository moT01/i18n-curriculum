---
id: bad87fee1348bd9aec908853
title: إضافة id Attributes إلی عناصر Bootstrap
challengeType: 0
forumTopicId: 16639
dashedName: add-id-attributes-to-bootstrap-elements
---

# --description--

Recall that in addition to class attributes, you can give each of your elements an `id` attribute.

يجب أن يكون كل معرف فريد لعنصر معين وأن يستخدم مرة واحدة فقط في الصفحة.

دعونا نعطي معرفًا فريدًا لكل عنصر من عناصر `div` الخاصة بالفئة `well`.

تذكر أنه يمكنك إعطاء عنصر معرف مثل:

```html
<div class="well" id="center-well">
```

أعط البئر على اليسار معرف (id) بقيمة `left-well`. أعط البئر على اليمين معرف (id) بقيمة `right-well`.

# --hints--

يجب أن يكون `well` في اليسار يحمل معرف (id) بقيمة `left-well`.

```js
const column = document.querySelectorAll('.col-xs-6')[0];
const leftWall = column?.querySelectorAll(`:scope ${'#left-well'}`);
assert.lengthOf(leftWall,1)
```

يجب أن يكون `well` في اليمين يحمل معرف (id) بقيمة `right-well`.

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
