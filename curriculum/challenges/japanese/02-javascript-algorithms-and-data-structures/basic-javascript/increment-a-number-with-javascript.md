---
id: 56533eb9ac21ba0edf2244ac
title: JavaScript で数値をインクリメントする
challengeType: 1
videoUrl: 'https://scrimba.com/c/ca8GLT9'
forumTopicId: 18201
dashedName: increment-a-number-with-javascript
---

# --description--

You can easily <dfn>increment</dfn> or add one to a variable with the `++` operator.

```js
i++;
```

は次の式と等価です。

```js
i = i + 1;
```

**注:** この行全体が `i++;` となり、等号が不要になります。

# --instructions--

コードを変更して `myVar` で `++` 演算子を使用してください。

# --hints--

`myVar` は `88` に等しくなる必要があります。

```js
assert(myVar === 88);
```

代入演算子は使用しないでください。

```js
assert(
  /let\s*myVar\s*=\s*87;\s*\/*.*\s*([+]{2}\s*myVar|myVar\s*[+]{2})/.test(__helpers.removeJSComments(code))
);
```

`++` 演算子を使用する必要があります。

```js
assert(/[+]{2}\s*myVar|myVar\s*[+]{2}/.test(__helpers.removeJSComments(code)));
```

指定のコメントより上にあるコードを変更しないでください。

```js
assert(/let myVar = 87;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myVar = ' + z;})(myVar);
```

## --seed-contents--

```js
let myVar = 87;

// Only change code below this line
myVar = myVar + 1;
```

# --solutions--

```js
let myVar = 87;
myVar++;
```
