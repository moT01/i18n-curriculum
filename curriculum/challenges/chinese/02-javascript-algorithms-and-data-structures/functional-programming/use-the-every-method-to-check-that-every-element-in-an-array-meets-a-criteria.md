---
id: 587d7dab367417b2b2512b6e
title: 使用 every 方法检查数组中的每个元素是否符合条件
challengeType: 1
forumTopicId: 301312
dashedName: use-the-every-method-to-check-that-every-element-in-an-array-meets-a-criteria
---

# --description--

The `every` method works with arrays to check if *every* element passes a particular test. It returns a Boolean value - `true` if all values meet the criteria, `false` if not.

举个例子，下面的代码检测数组 `numbers` 的所有元素是否都小于 10：

```js
const numbers = [1, 5, 8, 0, 10, 11];

numbers.every(function(currentValue) {
  return currentValue < 10;
});
```

`every` 方法在这里会返回 `false`。

# --instructions--

在 `checkPositive` 函数中使用 `every` 方法检查 `arr` 中是否所有元素都是正数。 函数应返回一个布尔值。

# --hints--

应使用`every`方法。

```js
assert(__helpers.removeJSComments(code).match(/\.every/g));
```

`checkPositive([1, 2, 3, -4, 5])` 应返回 `false`。

```js
assert.isFalse(checkPositive([1, 2, 3, -4, 5]));
```

`checkPositive([1, 2, 3, 4, 5])` 应返回 `true`。

```js
assert.isTrue(checkPositive([1, 2, 3, 4, 5]));
```

`checkPositive([1, -2, 3, -4, 5])` 应返回 `false`。

```js
assert.isFalse(checkPositive([1, -2, 3, -4, 5]));
```

# --seed--

## --seed-contents--

```js
function checkPositive(arr) {
  // Only change code below this line


  // Only change code above this line
}

checkPositive([1, 2, 3, -4, 5]);
```

# --solutions--

```js
function checkPositive(arr) {
  return arr.every(num => num > 0);
}
```
