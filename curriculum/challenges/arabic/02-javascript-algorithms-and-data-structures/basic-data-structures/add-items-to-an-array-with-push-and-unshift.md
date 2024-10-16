---
id: 587d78b2367417b2b2512b0e
title: إضافة عناصر إلى القائمة (array) باستخدام push() و unshift()
challengeType: 1
forumTopicId: 301151
dashedName: add-items-to-an-array-with-push-and-unshift
---

# --description--

An array's length, like the data types it can contain, is not fixed. Arrays can be defined with a length of any number of elements, and elements can be added or removed over time; in other words, arrays are <dfn>mutable</dfn>. In this challenge, we will look at two methods with which we can programmatically modify an array: `Array.push()` and `Array.unshift()`.

تأخذ كلتا الطريقتان (methods) عنصراً واحداً أو أكثر من العناصر كوسائط (parameters) وتضيف هذه العناصر إلى القائمة (array) التي تنفيذها الطريقة؛ تضيف طريقة `push()` عناصر إلى نهاية القائمة، وتضيف `unshift()` عناصر إلى البداية. انظر ما يلي:

```js
let twentyThree = 'XXIII';
let romanNumerals = ['XXI', 'XXII'];

romanNumerals.unshift('XIX', 'XX');
```

`romanNumerals` سيكون لها القيمة `['XIX', 'XX', 'XXI', 'XXII']`.

```js
romanNumerals.push(twentyThree);
```

`romanNumerals` سيكون لها القيمة `['XIX', 'XX', 'XXI', 'XXII', 'XXIII']`. لاحظ أنه يمكننا أيضا تمرير المتغيرات، مما يسمح لنا بمرونة أكبر في التعديل الديناميكي لبيانات القائمة.

# --instructions--

لقد حددنا الوظيفة `mixedNumbers`، التي سنمرر إليها قائمة كحجة. عدل الوظيفة باستخدام `push()` و `unshift()` لإضافة `'I', 2, 'three'` إلى بداية القائمة و `7, 'VIII', 9` إلي النهاية بحيث تحتوي القائمة المعادة على الأرقام 1-9 بالترتيب.

# --hints--

`mixedNumbers(["IV", 5, "six"])` الآن يجب أن ينتج `["I", 2, "three", "IV", 5, "six", 7, "VIII", 9]`

```js
assert.deepEqual(mixedNumbers(['IV', 5, 'six']), [
  'I',
  2,
  'three',
  'IV',
  5,
  'six',
  7,
  'VIII',
  9
]);
```

يجب أن تستخدم وظيفة `mixedNumbers` الطريقة `push()`

```js
assert(mixedNumbers.toString().match(/\.push/));
```

يجب أن تستخدم وظيفة `mixedNumbers` الطريقة `unshift()`

```js
assert(mixedNumbers.toString().match(/\.unshift/));
```

# --seed--

## --seed-contents--

```js
function mixedNumbers(arr) {
  // Only change code below this line

  // Only change code above this line
  return arr;
}

console.log(mixedNumbers(['IV', 5, 'six']));
```

# --solutions--

```js
function mixedNumbers(arr) {
  arr.push(7,'VIII',9);
  arr.unshift('I',2,'three');
  return arr;
}
```
