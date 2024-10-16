---
id: 587d7b7c367417b2b2512b1a
title: ブラケット記法によるプロパティ名へのアクセス
challengeType: 1
forumTopicId: 301150
dashedName: access-property-names-with-bracket-notation
---

# --description--

In the first object challenge we mentioned the use of bracket notation as a way to access property values using the evaluation of a variable. For instance, imagine that our `foods` object is being used in a program for a supermarket cash register. We have some function that sets the `selectedFood` and we want to check our `foods` object for the presence of that food. This might look like:

```js
let selectedFood = getCurrentFood(scannedItem);
let inventory = foods[selectedFood];
```

このコードは `selectedFood` 変数に保存されている値を評価し、`foods` オブジェクト内の該当するキーの値を返すか、キーが存在しない場合は `undefined` を返します。 実行時にオブジェクトのプロパティがわからない場合や、より動的な方法でのアクセスが必要な場合があるため、ブラケット記法は非常に便利です。

# --instructions--

関数 `checkInventory`を定義しました。これは引数としてスキャンしたアイテムを受け取ります。 `foods` オブジェクトの `scannedItem` キーの現在の値を返してください。 `checkInventory` の引数として有効なキーのみが与えられると仮定してかまいません。

# --hints--

`checkInventory` は関数でなければなりません。

```js
assert.strictEqual(typeof checkInventory, 'function');
```

`foods` オブジェクトには以下のキーと値のペアのみがあるものとします: `apples: 25`, `oranges: 32`, `plums: 28`, `bananas: 13`, `grapes: 35`, `strawberries: 27`

```js
assert.deepEqual(foods, {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
});
```

`checkInventory("apples")` は `25` を返す必要があります。

```js
assert.strictEqual(checkInventory('apples'), 25);
```

`checkInventory("bananas")` は `13` を返す必要があります。

```js
assert.strictEqual(checkInventory('bananas'), 13);
```

`checkInventory("strawberries")` は `27` を返す必要があります。

```js
assert.strictEqual(checkInventory('strawberries'), 27);
```

# --seed--

## --seed-contents--

```js
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

function checkInventory(scannedItem) {
  // Only change code below this line

  // Only change code above this line
}

console.log(checkInventory("apples"));
```

# --solutions--

```js
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

function checkInventory(scannedItem) {
  return foods[scannedItem];
}
```
