---
id: bad87fee1348bd9aed308826
title: Націльте батьківські елементи за допомогою jQuiery
challengeType: 6
forumTopicId: 18321
dashedName: target-the-parent-of-an-element-using-jquery
---

# --description--

Every HTML element has a `parent` element from which it `inherits` properties.

Наприклад, елемент `h3` в `jQuery Playground` має батьківський елемент `<div class="container-fluid">`, який теж має батьківський елемент `body`.

jQuery має функцію `parent()`, яка надає доступ до батьківських елементів будь-якого обраного елемента.

Ось приклад, як використати функцію `parent()`, щоб надати батьківському елементу елемента `left-well` синій фон:

```js
$("#left-well").parent().css("background-color", "blue")
```

Надайте батьківському елементу елемента `#target1` червоний фон.

# --hints--

Елемент `left-well` повинен мати червоний фон.

```js
assert(
  $('#left-well').css('background-color') === 'red' ||
    $('#left-well').css('background-color') === 'rgb(255, 0, 0)' ||
    $('#left-well').css('background-color').toLowerCase() === '#ff0000' ||
    $('#left-well').css('background-color').toLowerCase() === '#f00'
);
```

Використайте функцію `.parent()`, щоб змінити цей елемент.

```js
assert(code.match(/\.parent\s*\(\s*\)\s*\.css/g));
```

Викличте метод `.parent()` до елемента `#target1`.

```js
assert(
  code.match(/\$\s*?\(\s*?(?:'|")\s*?#target1\s*?(?:'|")\s*?\)\s*?\.parent/gi)
);
```

Для додавання цих класів використовуйте лише jQuery.

```js
assert(code.match(/<div class="well" id="left-well">/g));
```

# --seed--

## --seed-contents--

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
    $("#target1").prop("disabled", true);
    $("#target4").remove();
    $("#target2").appendTo("#right-well");
    $("#target5").clone().appendTo("#left-well");

  });
</script>

<!-- Only change code above this line -->

<body>
  <div class="container-fluid">
    <h3 class="text-primary text-center">jQuery Playground</h3>
    <div class="row">
      <div class="col-xs-6">
        <h4>#left-well</h4>
        <div class="well" id="left-well">
          <button class="btn btn-default target" id="target1">#target1</button>
          <button class="btn btn-default target" id="target2">#target2</button>
          <button class="btn btn-default target" id="target3">#target3</button>
        </div>
      </div>
      <div class="col-xs-6">
        <h4>#right-well</h4>
        <div class="well" id="right-well">
          <button class="btn btn-default target" id="target4">#target4</button>
          <button class="btn btn-default target" id="target5">#target5</button>
          <button class="btn btn-default target" id="target6">#target6</button>
        </div>
      </div>
    </div>
  </div>
</body>
```

# --solutions--

```html
<script>
  $(document).ready(function() {
    $("#target1").css("color", "red");
    $("#target1").prop("disabled", true);
    $("#target4").remove();
    $("#target2").appendTo("#right-well");
    $("#target5").clone().appendTo("#left-well");
    $("#target1").parent().css("background-color", "red");
  });
</script>

<!-- Only change code above this line -->

<body>
  <div class="container-fluid">
    <h3 class="text-primary text-center">jQuery Playground</h3>
    <div class="row">
      <div class="col-xs-6">
        <h4>#left-well</h4>
        <div class="well" id="left-well">
          <button class="btn btn-default target" id="target1">#target1</button>
          <button class="btn btn-default target" id="target2">#target2</button>
          <button class="btn btn-default target" id="target3">#target3</button>
        </div>
      </div>
      <div class="col-xs-6">
        <h4>#right-well</h4>
        <div class="well" id="right-well">
          <button class="btn btn-default target" id="target4">#target4</button>
          <button class="btn btn-default target" id="target5">#target5</button>
          <button class="btn btn-default target" id="target6">#target6</button>
        </div>
      </div>
    </div>
  </div>
</body>
```
