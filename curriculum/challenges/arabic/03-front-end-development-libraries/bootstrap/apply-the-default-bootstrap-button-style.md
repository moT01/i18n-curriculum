---
id: bad87fee1348bd9aec908850
title: تطبيق نمط الافتراضي إلي زر Bootstrap
challengeType: 0
forumTopicId: 16657
dashedName: apply-the-default-bootstrap-button-style
---

# --description--

Bootstrap has another button class called `btn-default`.

تطبيق كل من فئتي `btn` و `btn-default` على كل عنصر من عناصر `button`.

# --hints--

يجب عليك إضافة فئة `btn` إلى عنصر `button` الخاص بك.

```js
assert.lengthOf(document.querySelectorAll('.btn'),6);
```

يجب عليك إضافة فئة `btn-default` إلى عنصر `button` الخاص بك.

```js
assert.lengthOf(document.querySelectorAll('.btn-default'), 6);
```

# --seed--

## --seed-contents--

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

# --solutions--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <div class="well">
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
        <button class="btn btn-default"></button>
      </div>
    </div>
  </div>
</div>
```
