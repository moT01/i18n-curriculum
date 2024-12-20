---
id: 587d7b87367417b2b2512b43
title: 使用箭頭函數編寫簡潔的匿名函數
challengeType: 1
forumTopicId: 301211
dashedName: use-arrow-functions-to-write-concise-anonymous-functions
---

# --description--

In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.

這種情況下，我們通常會使用以下語法：

```js
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```

ES6 提供了其他寫匿名函數的方式的語法糖。 你可以使用**箭頭函數**：

```js
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```

當不需要函數體，只返回一個值的時候，箭頭函數允許你省略 `return` 關鍵字和外面的大括號。 這樣就可以將一個簡單的函數簡化成一個單行語句。

```js
const myFunc = () => "value";
```

這段代碼默認會返回字符串 `value`。

# --instructions--

使用箭頭函數的語法重寫賦給 `magic` 變量的函數，使其返回一個新的 Date() `new Date()`。 同時不要用 `var` 關鍵字來定義任何變量。

# --hints--

應替換 `var` 關鍵詞。

```js
assert.notMatch(code, /var/g)
```

`magic` 應該爲一個常量（使用 `const`）。

```js
assert.match(code, /const\s+magic/g)
```

`magic` 應該是一個函數 `function`。

```js
assert(typeof magic === 'function');
```

`magic()` 應該返回正確的日期。

```js
assert(magic().setHours(0, 0, 0, 0) === new Date().setHours(0, 0, 0, 0));
```

不能使用 `function` 關鍵字。

```js
assert.notMatch(code, /function/g)
```

# --seed--

## --seed-contents--

```js
var magic = function() {
  return new Date();
};
```

# --solutions--

```js
const magic = () => {
  return new Date();
};
```
