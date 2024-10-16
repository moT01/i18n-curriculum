---
id: 56bbb991ad1ed5201cd392d2
title: إضافة خصائص جديدة إلى كائن في JavaScript
challengeType: 1
videoUrl: 'https://scrimba.com/c/cQe38UD'
forumTopicId: 301169
dashedName: add-new-properties-to-a-javascript-object
---

# --description--

You can add new properties to existing JavaScript objects the same way you would modify them.

هذه هي طريقة إضافة خاصية `bark` إلى `ourDog`:

```js
ourDog.bark = "bow-wow";
```

أو

```js
ourDog["bark"] = "bow-wow";
```

الآن عندما نشغل `ourDog.bark`، سنحصل على صوت نُباحه `bow-wow`.

مثال:

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

# --instructions--

أضف خاصية `bark` إلى `myDog` وعيّنها إلى صوت الكلاب، مثل "woof". يمكنك استخدام أي من علامة نقط أو علامة الأقواس.

# --hints--

يجب عليك إضافة الخاصية `bark` إلى الكائن `myDog`.

```js
assert(myDog.bark !== undefined);
```

لا ينبغي أن تضيف `bark` إلى التعليمات البرمجية تهيئة الكائن `myDog`.

```js
assert(!/bark[^\n]:/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return z;})(myDog);
```

## --seed-contents--

```js
const myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};


```

# --solutions--

```js
const myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};
myDog.bark = "Woof Woof";
```
