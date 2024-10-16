---
id: 8d5823c8c441eddfaeb5bdef
title: マップデータ構造を作成する
challengeType: 1
forumTopicId: 301629
dashedName: create-a-map-data-structure
---

# --description--

The next few challenges will cover maps and hash tables. Maps are data structures that store key-value pairs. In JavaScript, these are available to us as objects. Maps provide rapid lookup of stored items based on key values and are very common and useful data structures.

# --instructions--

自分だけのマップを作る練習をしましょう。 JavaScript オブジェクトは、ここで書けるものよりもはるかに効率的なマップ構造を提供しているので、ここでの主な目的は学習のために練習することです。 ただし、JavaScript オブジェクトは特定の操作のみを提供します。 カスタム操作を定義したい場合はどうなるでしょう？ ここで提供されている `Map` オブジェクトを JavaScript `object` のラッパーとして使用します。 Map オブジェクトに対する以下のメソッドと操作を作成してください。

<ul>
<li><code>add</code> accepts a <code>key, value</code> pair to add to the map.</li>
<li><code>remove</code> はキーを受け入れ、関連付けられた <code>key、value</code> のペア を削除します</li>
<li><code>get</code> は <code>key</code> を受け入れ、格納された <code>value</code> を返します</li>
<li><code>has</code> は <code>key</code> を受け入れ、キーが存在する場合は <dfn>true</dfn> を返し、そうでない場合は <dfn>false</dfn> を返します</li>
<li><code>values</code> はマップ内のすべての値の配列を返します</li>
<li><code>size</code> はマップ内の要素数を返します</li>
<li><code>clear</code> はマップを空にします</li>
</ul>

# --hints--

`Map` データ構造を用意する必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    return typeof test == 'object';
  })()
);
```

`Map` オブジェクトには以下のメソッドが必要です: `add`, `remove`, `get`, `has`, `values`, `clear`, `size`

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    return (
      typeof test.add == 'function' &&
      typeof test.remove == 'function' &&
      typeof test.get == 'function' &&
      typeof test.has == 'function' &&
      typeof test.values == 'function' &&
      typeof test.clear == 'function' &&
      typeof test.size == 'function'
    );
  })()
);
```

`add` メソッドはマップに要素を追加する必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    test.add(5, 6);
    test.add(2, 3);
    test.add(2, 5);
    return test.size() == 2;
  })()
);
```

`has` メソッドは、追加された要素に対して `true` を、存在しない要素に対して `false` を返す必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    test.add('test', 'value');
    return test.has('test') && !test.has('false');
  })()
);
```

`get` メソッドはキーを入力として受け入れ、関連付けられた値を返す必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    test.add('abc', 'def');
    return test.get('abc') == 'def';
  })()
);
```

`values` メソッドは、マップに格納されているすべての値を、文字列の配列として返す必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    test.add('a', 'b');
    test.add('c', 'd');
    test.add('e', 'f');
    var vals = test.values();
    return (
      vals.indexOf('b') != -1 &&
      vals.indexOf('d') != -1 &&
      vals.indexOf('f') != -1
    );
  })()
);
```

`clear` メソッドはマップを空にし、`size` メソッドはマップに存在する要素の数を返す必要があります。

```js
assert(
  (function () {
    var test = false;
    if (typeof Map !== 'undefined') {
      test = new Map();
    }
    test.add('b', 'b');
    test.add('c', 'd');
    test.remove('asdfas');
    var init = test.size();
    test.clear();
    return init == 2 && test.size() == 0;
  })()
);
```

# --seed--

## --seed-contents--

```js
var Map = function() {
  this.collection = {};
  // Only change code below this line

  // Only change code above this line
};
```

# --solutions--

```js
var Map = function() {
    this.collection = {};
    // Only change code below this line

    this.add = function(key,value) {
      this.collection[key] = value;
    }

    this.remove = function(key) {
      delete this.collection[key];
    }

    this.get = function(key) {
      return this.collection[key];
    }

    this.has = function(key) {
      return this.collection.hasOwnProperty(key)
    }

    this.values = function() {
      return Object.values(this.collection);
    }

    this.size = function() {
      return Object.keys(this.collection).length;
    }

    this.clear = function() {
      for(let item of Object.keys(this.collection)) {
        delete this.collection[item];
      }
    }
    // Only change code above this line
};
```
