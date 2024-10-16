---
id: 56533eb9ac21ba0edf2244ba
title: فهم عدم قابلية المقطع على التغيير (String Immutability)
challengeType: 1
videoUrl: 'https://scrimba.com/c/cWPVaUR'
forumTopicId: 18331
dashedName: understand-string-immutability
---

# --description--

In JavaScript, `String` values are <dfn>immutable</dfn>, which means that they cannot be altered once created.

على سبيل المثال الكود التالي سينتج خطأ لأن الحرف `B` في المقطع النصي `Bob` لا يمكن تغييره إلى حرف `J`:

```js
let myStr = "Bob";
myStr[0] = "J";
```

لاحظ أن هذا *لا* يعني أنه لا يمكن إعادة تعيين `myStr`. الطريقة الوحيدة لتغيير `myStr` هي تعيينه بمقطع جديد، هكذا:

```js
let myStr = "Bob";
myStr = "Job";
```

# --instructions--

صحّح تعيين `myStr` بحيث يحتوي على قيمة المقطع النصي `Hello World` باستخدام الطريقة الموضحة في المثال أعلاه.

# --hints--

يجب أن يكون لدي `myStr` قيمة المقطع الآتي `Hello World`.

```js
assert(myStr === 'Hello World');
```

لا يجب عليك تعديل الكود فوق التعليق المحدد.

```js
assert(/myStr = "Jello World"/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(v){return "myStr = " + v;})(myStr);
```

## --seed-contents--

```js
// Setup
let myStr = "Jello World";

// Only change code below this line
myStr[0] = "H"; // Change this line
// Only change code above this line
```

# --solutions--

```js
let myStr = "Jello World";
myStr = "Hello World";
```
