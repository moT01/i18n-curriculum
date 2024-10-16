---
id: 587d78b3367417b2b2512b11
title: Splice() によるアイテムの追加
challengeType: 1
forumTopicId: 301152
dashedName: add-items-using-splice
---

# --description--

Remember in the last challenge we mentioned that `splice()` can take up to three parameters? Well, you can use the third parameter, comprised of one or more element(s), to add to the array. This can be incredibly useful for quickly switching out an element, or a set of elements, for another.

```js
const numbers = [10, 11, 12, 12, 15];
const startIndex = 3;
const amountToDelete = 1;

numbers.splice(startIndex, amountToDelete, 13, 14);
console.log(numbers);
```

2 つ目の重複する `12` は削除され、同じインデックスに `13` と `14` が追加されます。 これで `numbers` 配列は `[ 10, 11, 12, 13, 14, 15 ]` となります。

ここでは、最初に数字の配列があります。 次に、`splice()` に、要素の削除を開始するインデックス (3) と、削除する要素の数 (1)、そして、同じインデックスに順に挿入される残りの引数 (13, 14) を渡します。 `amountToDelete` の後に、任意の数の要素 (コンマで区切る) を指定でき、それぞれを挿入できることに注意してください。

# --instructions--

関数 `htmlColorNames`を定義しました。これは、引数として HTML カラーの配列を取ります。 `splice()` を使用して関数を変更してください。配列の最初の 2 つの要素を削除し、それぞれの場所に `'DarkSalmon'` と `'BlanchedAlmond'` を追加します。

# --hints--

`htmlColorNames` は `["DarkSalmon", "BlanchedAlmond", "LavenderBlush", "PaleTurquoise", "FireBrick"]` を返す必要があります。

```js
assert.deepEqual(
  htmlColorNames([
    'DarkGoldenRod',
    'WhiteSmoke',
    'LavenderBlush',
    'PaleTurquoise',
    'FireBrick'
  ]),
  [
    'DarkSalmon',
    'BlanchedAlmond',
    'LavenderBlush',
    'PaleTurquoise',
    'FireBrick'
  ]
);
```

`htmlColorNames` 関数で `splice()` メソッドを使用する必要があります。

```js
assert(/.splice/.test(__helpers.removeJSComments(code)));
```

`shift()` または `unshift()` は使用しないでください。

```js
assert(!/shift|unshift/.test(__helpers.removeJSComments(code)));
```

配列ブラケット記法は使用しないでください。

```js
assert(!/\[\d\]\s*=/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function htmlColorNames(arr) {
  // Only change code below this line

  // Only change code above this line
  return arr;
}

console.log(htmlColorNames(['DarkGoldenRod', 'WhiteSmoke', 'LavenderBlush', 'PaleTurquoise', 'FireBrick']));
```

# --solutions--

```js
function htmlColorNames(arr) {
  arr.splice(0,2,'DarkSalmon', 'BlanchedAlmond');
  return arr;
}
```
