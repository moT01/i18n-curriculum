---
id: 587d7b8c367417b2b2512b57
title: استخدم * لاستيراد كل شيء من ملف (Use * to Import Everything from a File)
challengeType: 1
forumTopicId: 301210
dashedName: use--to-import-everything-from-a-file
---

# --description--

Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the `import * as` syntax. Here's an example where the contents of a file named `math_functions.js` are imported into a file in the same directory:

```js
import * as myMathModule from "./math_functions.js";
```

سيتم في بيان الاستيراد `import` أعلاه إنشاء object يسمى `myMathModule`. هذا مجرد اسم متغير، يمكنك تسميته أي شيء. سيحتوي الـ object على جميع الصادرات من `math_functions.js` بداخله، فيمكنك استخدام الـ functions مثل أي object property آخري. إليك كيف يمكنك استخدام دالة `add` و `subtract` التي تم استيرادهم:

```js
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```

# --instructions--

يتطلب الكود في هذا الملف محتويات الملف: `string_functions.js`، وذلك في نفس المجلد مثل الملف الحالي. استخدم `import * as` لاستيراد كل شيء من الملف إلى object يسمى `stringFunctions`.

# --hints--

يجب أن يستخدم الكود الخاص بك `import * as` بشكل صحيح.

```js
assert(
  __helpers.removeJSComments(code).match(
    /import\s*\*\s*as\s+stringFunctions\s+from\s*('|")\.\/string_functions\.js\1/g
  )
);
```

# --seed--

## --seed-contents--

```js

// Only change code above this line

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

# --solutions--

```js
import * as stringFunctions from "./string_functions.js";

// add code above this line
stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```
