---
id: 5ee127a03c3b35dd45426493
title: ある変数の値を別の変数に割り当てる
challengeType: 1
forumTopicId: 418265
dashedName: assigning-the-value-of-one-variable-to-another
---

# --description--

After a value is assigned to a variable using the <dfn>assignment</dfn> operator, you can assign the value of that variable to another variable using the <dfn>assignment</dfn> operator.

```js
var myVar;
myVar = 5;
var myNum;
myNum = myVar;
```

上記は値を持たない `myVar` 変数を宣言したあと、値 `5` を代入します。 次に、値を持たない `myNum` という名前の変数を宣言します。 そして、`myVar` の内容 (値 `5`) が変数 `myNum` に割り当てられます。 最終的に、`myNum` の値も `5` になりました。

# --instructions--

変数 `a` の内容を変数 `b` に割り当ててください。

# --hints--

指定のコメントより上にあるコードを変更しないでください。

```js
assert(/var a;/.test(__helpers.removeJSComments(code)) && /a = 7;/.test(__helpers.removeJSComments(code)) && /var b;/.test(__helpers.removeJSComments(code)));
```

`b` の値は `7` でなければなりません。

```js
assert(typeof b === 'number' && b === 7);
```

`a` は `=` を使って `b` に割り当てられなければなりません。

```js
assert(/b\s*=\s*a\s*/g.test(__helpers.removeJSComments(code)));
```

# --seed--

## --before-user-code--

```js
if (typeof a != 'undefined') {
  a = undefined;
}
if (typeof b != 'undefined') {
  b = undefined;
}
```

## --after-user-code--

```js
(function(a, b) {
  return 'a = ' + a + ', b = ' + b;
})(a, b);
```

## --seed-contents--

```js
// Setup
var a;
a = 7;
var b;

// Only change code below this line
```

# --solutions--

```js
var a;
a = 7;
var b;
b = a;
```
