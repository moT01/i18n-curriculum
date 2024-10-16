---
id: 587d7b86367417b2b2512b3b
title: التقاط أخطاء يفتقد واحد (Off By One Errors) عند استخدام الترتيب
challengeType: 1
forumTopicId: 301189
dashedName: catch-off-by-one-errors-when-using-indexing
---

# --description--

<dfn>Off by one errors</dfn> (sometimes called OBOE) crop up when you're trying to target a specific index of a string or array (to slice or access a segment), or when looping over the indices of them. JavaScript indexing starts at zero, not one, which means the last index is always one less than the length of the item. If you try to access an index equal to the length, the program may throw an "index out of range" reference error or print `undefined`.

عندما تستخدم طرق المقطع أو القائمة التي تأخذ نطاقات الترتيب كحجج، فمن المفيد قراءة الوثائق (documentation) وفهم ما إذا كانت شاملة (العنصر في الترتيب المحدد هو جزء مما تم إرجاعه) أم لا. وفيما يلي بعض الأمثلة عن الأخطاء من نوع يفتقد واحد:

```js
let alphabet = "abcdefghijklmnopqrstuvwxyz";
let len = alphabet.length;
for (let i = 0; i <= len; i++) {
  console.log(alphabet[i]);
}
for (let j = 1; j < len; j++) {
  console.log(alphabet[j]);
}
for (let k = 0; k < len; k++) {
  console.log(alphabet[k]);
}
```

المثال الأول هنا يتكرر عدة مرات، والثاني يتكرر مرات قليلة (ينقصه الترتيب الأول، 0). المثال الثالث صحيح.

# --instructions--

أصحّح أخطاء الترتيب في الوظيفة (function) التالية بحيث يتم طباعة جميع الأرقام من 1 إلى 5 إلى وحدة التحكم.

# --hints--

يجب أن يقوم الكود الخاص بك بتعيين الشرط الأولي للحلقة (loop) بحيث يبدأ من الترتيب الأول.

```js
assert(__helpers.removeJSComments(code).match(/i\s*?=\s*?0\s*?;/g).length == 1);
```

يجب أن يقوم الكود الخاص بك بإصلاح الشرط الأولي للحلقة بحيث يبدأ الترتيب من 0.

```js
assert(!__helpers.removeJSComments(code).match(/i\s?=\s*?1\s*?;/g));
```

يجب أن يضبط الكود الخاص بك الشرط الطرفي (terminal condition) للحلقة بحيث يتوقف عند الترتيب الأخير.

```js
assert(__helpers.removeJSComments(code).match(/i\s*<\s*len\s*;|i\s*<=\s*len\s*-\s*1\s*;/g).length == 1);
```

يجب أن يصلح الكود الخاص بك الشرط الطرفي للحلقة بحيث يتوقف عند 1 قبل الطول.

```js
assert(!__helpers.removeJSComments(code).match(/i\s*?<=\s*?len;/g));
```

# --seed--

## --seed-contents--

```js
function countToFive() {
  let firstFive = "12345";
  let len = firstFive.length;
  // Only change code below this line
  for (let i = 1; i <= len; i++) {
  // Only change code above this line
    console.log(firstFive[i]);
  }
}

countToFive();
```

# --solutions--

```js
function countToFive() {
 let firstFive = "12345";
 let len = firstFive.length;
 // Only change code below this line
 for (let i = 0; i < len; i++) {
 // Only change code above this line
   console.log(firstFive[i]);
 }
}

countToFive();
```
