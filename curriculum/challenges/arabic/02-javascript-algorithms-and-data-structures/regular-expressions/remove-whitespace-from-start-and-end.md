---
id: 587d7dbb367417b2b2512bac
title: إزالة Whitespace من البداية و النهاية (Remove Whitespace from Start and End)
challengeType: 1
forumTopicId: 301362
dashedName: remove-whitespace-from-start-and-end
---

# --description--

Sometimes whitespace characters around strings are not wanted but are there. Typical processing of strings is to remove the whitespace at the start and end of it.

# --instructions--

اكتب regex و استخدم الطرق المناسبة لإزالة الـ whitespace في بداية و نهاية الـ strings.

**ملاحظة:** طريقة `String.prototype.trim()` ستعمل هنا، ولكن ستحتاج إلى إكمال هذا التحدي باستخدام regular expressions.

# --hints--

`result` يجب أن تكون مساوية للـ string الآتي `Hello, World!`

```js
assert(result === 'Hello, World!');
```

يجب ألا يستخدم حلك طريقة `String.prototype.trim()`.

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?trim/));
```

متغير النتيجة `result` يجب ألا يتم تعيينه مباشرة إلى string

```js
assert(!__helpers.removeJSComments(code).match(/result\s*=\s*["'`].*?["'`]/));
```

لا ينبغي تغيير قيمة متغير `hello`.

```js
assert(hello === '   Hello, World!  ');
```

# --seed--

## --seed-contents--

```js
let hello = "   Hello, World!  ";
let wsRegex = /change/; // Change this line
let result = hello; // Change this line
```

# --solutions--

```js
let hello = "   Hello, World!  ";
let wsRegex = /^(\s+)(.+[^\s])(\s+)$/;
let result = hello.replace(wsRegex, '$2');
```
