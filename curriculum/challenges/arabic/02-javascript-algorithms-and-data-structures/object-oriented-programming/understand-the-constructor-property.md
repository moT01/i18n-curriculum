---
id: 587d7daf367417b2b2512b7e
title: Understand the Constructor Property
challengeType: 1
forumTopicId: 301327
dashedName: understand-the-constructor-property
---

# --description--

There is a special `constructor` property located on the object instances `duck` and `beagle` that were created in the previous challenges:

```js
let duck = new Bird();
let beagle = new Dog();

console.log(duck.constructor === Bird); 
console.log(beagle.constructor === Dog);
```

كل من هذه الاستدعائات لـ `console.log` سوف تعرض `true` في وحدة التحكم.

لاحظ أن خاصية الـ `constructor` هي مرجع للـ constructor function التي أنشأت الـ instance. ميزة خاصية للـ `constructor` هي أنه من الممكن التحقق من هذه الخاصية لمعرفة نوع الـ object. اليك مثال على كيفية استخدام هذا:

```js
function joinBirdFraternity(candidate) {
  if (candidate.constructor === Bird) {
    return true;
  } else {
    return false;
  }
}
```

**ملاحظة:** بما أن خاصية الـ `constructor` يمكن الكتابة عليها (والتي سيتم تغطيتها في التحديين التاليين) من الأفضل عموماً استخدام `instanceof` للتحقق من نوع الـ object.

# --instructions--

اكتب وظيفة `joinDogFraternity` التي تأخذ وسيط `candidate`, وتستخدم خاصية `constructor`, لتنتج `true` عندما يكون قيمة candidate تساوي `Dog`، وتنتح `false` عندما لا يكون كذلك.

# --hints--

`joinDogFraternity` يجب تعريفه كـ function.

```js
assert(typeof joinDogFraternity === 'function');
```

`joinDogFraternity` يجب أن يرجع `true` إذا كان `candidate` هو instance لـ `Dog`.

```js
assert(joinDogFraternity(new Dog('')) === true);
```

`joinDogFraternity` يجب أن تستخدم خاصية الـ `constructor`.

```js
assert(/\.constructor/.test(__helpers.removeJSComments(code)) && !/instanceof/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function Dog(name) {
  this.name = name;
}

// Only change code below this line
function joinDogFraternity(candidate) {

}
```

# --solutions--

```js
function Dog(name) {
  this.name = name;
}
function joinDogFraternity(candidate) {
  return candidate.constructor === Dog;
}
```
