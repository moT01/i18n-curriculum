---
id: 587d7dae367417b2b2512b7a
title: 使用 instanceof 验证对象的构造函数
challengeType: 1
forumTopicId: 301337
dashedName: verify-an-objects-constructor-with-instanceof
---

# --description--

Anytime a constructor function creates a new object, that object is said to be an <dfn>instance</dfn> of its constructor. JavaScript gives a convenient way to verify this with the `instanceof` operator. `instanceof` allows you to compare an object to a constructor, returning `true` or `false` based on whether or not that object was created with the constructor. 如下所示：

```js
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird;
```

`instanceof` 方法会返回 `true`。

如果一个对象不是使用构造函数创建的，那么 `instanceof` 将会验证这个对象不是构造函数的实例：

```js
let canary = {
  name: "Mildred",
  color: "Yellow",
  numLegs: 2
};

canary instanceof Bird;
```

`instanceof` 方法会返回 `false`。

# --instructions--

给 `House` 构造函数创建一个新实例，取名为 `myHouse`，并且传递一个数字给 bedrooms 参数。 然后使用 `instanceof` 操作符验证这个对象是否为 `House` 的实例。

# --hints--

`myHouse` 应该有一个 `numBedrooms` 属性值被赋为一个数字。

```js
assert(typeof myHouse.numBedrooms === 'number');
```

应该使用 `instanceof` 操作符验证 `myHouse` 这个对象是 `House` 构造函数的一个实例。

```js
assert(/myHouse\s*instanceof\s*House/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function House(numBedrooms) {
  this.numBedrooms = numBedrooms;
}

// Only change code below this line
```

# --solutions--

```js
function House(numBedrooms) {
  this.numBedrooms = numBedrooms;
}
const myHouse = new House(4);
console.log(myHouse instanceof House);
```
