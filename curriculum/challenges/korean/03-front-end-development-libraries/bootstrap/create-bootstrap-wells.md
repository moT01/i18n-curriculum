---
id: bad87fee1348bd9aec908848
title: 부트스트랩 well 생성하기
challengeType: 0
forumTopicId: 16825
dashedName: create-bootstrap-wells
---

# --description--

Bootstrap has a class called `well` that can create a visual sense of depth for your columns.

`well` 클래스를 가진 `div` 요소를 각각의 `col-xs-6` `div` 요소 내에 중첩합니다.

# --hints--

`col-xs-6` 클래스를 가진 `div` 요소 내에 `well` 클래스를 가진 `div` 요소를 추가해야 합니다.

```js
const wells = document.querySelectorAll('div.col-xs-6 > div.well');
assert.lengthOf( wells,2 ); 
```

`col-xs-6` 클래스를 가진 `div` 요소는 `row` 클래스를 가진 `div` 요소 내에 중첩되어야 합니다.

```js
assert.lengthOf(document.querySelectorAll('div.row > div.col-xs-6'),2);
```

모든 `div` 요소는 닫는 태그를 가져야 합니다.

```js
assert.match(code,/<\/div>/g);
assert.match(code,/<div/g);
assert.equal(code.match(/<\/div>/g)?.length , code.match(/<div/g)?.length);
```

# --seed--

## --seed-contents--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">

    </div>
    <div class="col-xs-6">

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
      <div class="well"></div>
    </div>
    <div class="col-xs-6">
      <div class="well"></div>
    </div>
  </div>
</div>
```
