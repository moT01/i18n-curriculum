---
id: 587d7b89367417b2b2512b4b
title: 分割代入を使用して配列から変数を代入する
challengeType: 1
forumTopicId: 301213
dashedName: use-destructuring-assignment-to-assign-variables-from-arrays
---

# --description--

ES6 makes destructuring arrays as easy as destructuring objects.

スプレッド演算子と配列分割の重要な違いは、スプレッド演算子は配列のすべての内容をカンマ区切りのリストに展開することです。 したがって、どの要素をどの変数に代入するかを選ぶことはできません。

配列の分割では、まさにそれを行うことができます。

```js
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b);
```

コンソールは `a` と `b` の値を `1, 2` と表示します。

変数 `a` には配列の最初の値が代入され、 `b` には配列の 2 番目の値が代入されます。 目的のインデックスに到達するためにカンマを利用して分割することにより、配列内の任意のインデックスの値にアクセスすることもできます。

```js
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c);
```

コンソールは `a` と `b` と `c` の値を `1, 2, 5` と表示します。

# --instructions--

分割代入を使用して `a` と `b` の値を入れ替え、`b` に保存されている値を `a` が受け取り、`a` に保存されている値を `b` が受け取るようにしてください。

# --hints--

`a` の値は入れ替え後に `6` となります。

```js
assert(a === 6);
```

`b` の値は入れ替え後に `8` となります。

```js
assert(b === 8);
```

配列の分割を使用して `a` と `b` を入れ替える必要があります。

```js
assert(/\[\s*(\w)\s*,\s*(\w)\s*\]\s*=\s*\[\s*\2\s*,\s*\1\s*\]/g.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
let a = 8, b = 6;
// Only change code below this line
```

# --solutions--

```js
let a = 8, b = 6;
[a, b] = [b, a];
```
