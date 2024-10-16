---
id: 587d7da9367417b2b2512b6a
title: 元の配列を変更せずにソートされた配列を返す
challengeType: 1
forumTopicId: 301237
dashedName: return-a-sorted-array-without-changing-the-original-array
---

# --description--

A side effect of the `sort` method is that it changes the order of the elements in the original array. In other words, it mutates the array in place. One way to avoid this is to first concatenate an empty array to the one being sorted (remember that `slice` and `concat` return a new array), then run the `sort` method.

# --instructions--

`nonMutatingSort` 関数で `sort` メソッドを使用して、配列の要素を昇順でソートしてください。 この関数は新しい配列を返し、`globalArray` 変数をミューテートさせないようにする必要があります。

# --hints--

コードで `sort` メソッドを使用する必要があります。

```js
assert(nonMutatingSort.toString().match(/\.sort/g));
```

`globalArray` 変数は変更しないでください。

```js
assert(JSON.stringify(globalArray) === JSON.stringify([5, 6, 3, 2, 9]));
```

`nonMutatingSort(globalArray)` は `[2, 3, 5, 6, 9]` を返す必要があります。

```js
assert(
  JSON.stringify(nonMutatingSort(globalArray)) ===
    JSON.stringify([2, 3, 5, 6, 9])
);
```

`nonMutatingSort(globalArray)` をハードコーディングしないでください。

```js
assert(!nonMutatingSort.toString().match(/\[.*?[23569].*?\]/gs));
```

この関数は、渡された配列ではなく、新しい配列を返す必要があります。

```js
assert(nonMutatingSort(globalArray) !== globalArray);
```

`nonMutatingSort([1, 30, 4, 21, 100000])` は `[1, 4, 21, 30, 100000]` を返す必要があります。

```js
assert(JSON.stringify(nonMutatingSort([1, 30, 4, 21, 100000])) ===
    JSON.stringify([1, 4, 21, 30, 100000]))
```

`nonMutatingSort([140000, 104, 99])` は `[99, 104, 140000]` を返す必要があります。

```js
assert(JSON.stringify(nonMutatingSort([140000, 104, 99])) ===
    JSON.stringify([99, 104, 140000]))
```

# --seed--

## --seed-contents--

```js
const globalArray = [5, 6, 3, 2, 9];

function nonMutatingSort(arr) {
  // Only change code below this line


  // Only change code above this line
}

nonMutatingSort(globalArray);
```

# --solutions--

```js
const globalArray = [5, 6, 3, 2, 9];
function nonMutatingSort(arr) {
  return [].concat(arr).sort((a,b) => a-b);
}
```
