---
id: 587d7db0367417b2b2512b81
title: 객체의 프로토타입의 근원 이해하기
challengeType: 1
forumTopicId: 301330
dashedName: understand-where-an-objects-prototype-comes-from
---

# --description--

Just like people inherit genes from their parents, an object inherits its `prototype` directly from the constructor function that created it. For example, here the `Bird` constructor creates the `duck` object:

```js
function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");
```

`duck`은 생성자 함수 `Bird`로부터 `prototype`을 상속받습니다. `isPrototypeOf` 메소드를 통해 이 관계를 확인할 수 있습니다.

```js
Bird.prototype.isPrototypeOf(duck);
```

이것은 `true`를 반환할 것입니다.

# --instructions--

`beagle`의 `prototype`을 확인하기 위해 `isPrototypeOf`을 사용하시오.

# --hints--

`Dog.prototype`은 `beagle`의 `prototype`이라는 것을 보여줘야 합니다.

```js
assert(/Dog\.prototype\.isPrototypeOf\(beagle\)/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

// Only change code below this line
```

# --solutions--

```js
function Dog(name) {
  this.name = name;
}
let beagle = new Dog("Snoopy");
Dog.prototype.isPrototypeOf(beagle);
```
