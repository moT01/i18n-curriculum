---
id: 56533eb9ac21ba0edf2244da
title: مقدمة ألى تعبيرات Else
challengeType: 1
videoUrl: 'https://scrimba.com/c/cek4Efq'
forumTopicId: 18207
dashedName: introducing-else-statements
---

# --description--

When a condition for an `if` statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an `else` statement, an alternate block of code can be executed.

```js
if (num > 10) {
  return "Bigger than 10";
} else {
  return "10 or Less";
}
```

# --instructions--

ادمج عبارات `if` في عبارة واحدة `if/else`.

# --hints--

يجب أن يكون لديك عبارة `if` واحدة فقط في المحرر

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

يجب عليك استخدام عبارة `else`

```js
assert(/else/g.test(__helpers.removeJSComments(code)));
```

يجب أن تنتج `testElse(4)` المقطع النصي `5 or Smaller`

```js
assert(testElse(4) === '5 or Smaller');
```

يجب أن تنتج `testElse(5)` المقطع النصي `5 or Smaller`

```js
assert(testElse(5) === '5 or Smaller');
```

يجب أن تنتج `testElse(6)` المقطع النصي`Bigger than 5`

```js
assert(testElse(6) === 'Bigger than 5');
```

يجب أن تنتج `testElse(10)` المقطع النصي`Bigger than 5`

```js
assert(testElse(10) === 'Bigger than 5');
```

لا يجب عليك تعديل الكود فوق التعليق المحدد.

```js
assert(/let result = "";/.test(__helpers.removeJSComments(code)) && /return result;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function testElse(val) {
  let result = "";
  // Only change code below this line

  if (val > 5) {
    result = "Bigger than 5";
  }

  if (val <= 5) {
    result = "5 or Smaller";
  }

  // Only change code above this line
  return result;
}

testElse(4);
```

# --solutions--

```js
function testElse(val) {
  let result = "";
  if(val > 5) {
    result = "Bigger than 5";
  } else {
    result = "5 or Smaller";
  }
  return result;
}
```
