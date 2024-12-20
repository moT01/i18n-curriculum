---
id: 587d7db0367417b2b2512b83
title: 使用繼承避免重複
challengeType: 1
forumTopicId: 301334
dashedName: use-inheritance-so-you-dont-repeat-yourself
---

# --description--

There's a principle in programming called <dfn>Don't Repeat Yourself (DRY)</dfn>. The reason repeated code is a problem is because any change requires fixing code in multiple places. This usually means more work for programmers and more room for errors.

請觀察下面的示例，`Bird` 和 `Dog` 共享 `describe` 方法：

```js
Bird.prototype = {
  constructor: Bird,
  describe: function() {
    console.log("My name is " + this.name);
  }
};

Dog.prototype = {
  constructor: Dog,
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

我們可以看到 `describe` 方法在兩個地方重複定義了。 根據以上所說的 DRY 原則，我們可以通過創建一個 `Animal` `supertype`（或者父類）來重寫這段代碼：

```js
function Animal() { };

Animal.prototype = {
  constructor: Animal, 
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

`Animal` 構造函數中定義了 `describe` 方法，可將 `Bird` 和 `Dog` 這兩個構造函數的方法刪除掉：

```js
Bird.prototype = {
  constructor: Bird
};

Dog.prototype = {
  constructor: Dog
};
```

# --instructions--

`Cat` 和 `Bear` 重複定義了 `eat` 方法。 本着 DRY 的原則，通過將 `eat` 方法移動到 `Animal` `supertype` 中來重寫你的代碼。

# --hints--

`Animal.prototype` 應該有 `eat` 屬性。

```js
assert(Animal.prototype.hasOwnProperty('eat'));
```

`Bear.prototype` 不應該有 `eat` 屬性。

```js
assert(!Bear.prototype.hasOwnProperty('eat'));
```

`Cat.prototype` 不應該有 `eat` 屬性。

```js
assert(!Cat.prototype.hasOwnProperty('eat'));
```

# --seed--

## --seed-contents--

```js
function Cat(name) {
  this.name = name;
}

Cat.prototype = {
  constructor: Cat,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Bear(name) {
  this.name = name;
}

Bear.prototype = {
  constructor: Bear,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Animal() { }

Animal.prototype = {
  constructor: Animal,

};
```

# --solutions--

```js
function Cat(name) {
  this.name = name;
}

Cat.prototype = {
  constructor: Cat
};

function Bear(name) {
  this.name = name;
}

Bear.prototype = {
  constructor: Bear
};

function Animal() { }

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};
```
