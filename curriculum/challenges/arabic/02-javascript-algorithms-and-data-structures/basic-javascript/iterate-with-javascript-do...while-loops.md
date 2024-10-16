---
id: 5a2efd662fb457916e1fe604
title: التكرار مع الحلَقات Do...While في JavaScript
challengeType: 1
videoUrl: 'https://scrimba.com/c/cDqWGcp'
forumTopicId: 301172
dashedName: iterate-with-javascript-do---while-loops
---

# --description--

The next type of loop you will learn is called a `do...while` loop. It is called a `do...while` loop because it will first `do` one pass of the code inside the loop no matter what, and then continue to run the loop `while` the specified condition evaluates to `true`.

```js
const ourArray = [];
let i = 0;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

المثال أعلاه يتصرف بطريقة مشابهة للأنواع الأخرى من حلَقات، والحلقة الناتجة عنه ستبدو مثل `[0, 1, 2, 3, 4]`. ومع ذلك، فإن ما يجعل `do...while` يختلف عن الحلَقات الأخرى هو كيف يتصرف عندما يفشل الشرط في الفحص الأول. سوف ترى هذا في الواقع. إليك حلقة `while` عادية, سوف يشغل الكود الحلقة (loop) مادام أن `i < 5`:

```js
const ourArray = []; 
let i = 5;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```

في هذا المثال، نقوم بتهيئة قيمة `ourArray` إلى قائمة (array) فارغة وقيمة `i` إلى 5. عندما تنفيذ حلقة `while`, يتم تقييم الشرط إلى `false` لأن `i` لم يقل عن 5، لذلك نحن لا ننفذ الكود داخل الحلقة. والنتيجة هي أن `ourArray` سينتهي به الأمر إلى عدم إضافة قيم إليه، وسيظل يبدو مثل `[]` عندما يكون الكود في المثال أعلاه قد انتهي من التنفيذ. الآن، ألقي النَّظْرَة على حلقة `do...while`:

```js
const ourArray = []; 
let i = 5;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

في هذه الحالة، نقوم بتهيئة قيمة `i` إلى 5، تماما كما فعلنا مع حلقة `while`. عندما نصل إلى السطر التالي، لا يوجد شرط للتقييم، لذا نذهب إلى الكود داخل الأقواس {} وننفذه. سوف نضيف عنصرا واحدا إلى القائمة ثم نزيد `i` قبل أن نصل إلى التحقق من الشرط. عندما نقوم أخيرا بتقييم الشرط `i < 5` في السطر الأخير، نحن نرى أن `i` هو 6 الآن، و بالتالي أخفق في الفحص الشرطي، لذلك الخروج من الحلقة و ينتهي التنفيذ. في نهاية المثال الوارد أعلاه، قيمة `ourArray` هي `[5]`. في الأساس `do...while` تضمن أن الكود داخل الحلقة سوف يعمل مرة واحدة في الأقل. حاول جعل `do...while` تعمل عن طريق أضافه القيم إلى القائمة.

# --instructions--

غيّر `while` في الكود إلى `do...while` حتى تقوم الحلقة بإضافة فقط الرَّقْم `10` إلى `myArray`، و `i` سيكون مساويا ألى `11` عند الانتهاء من تشغيل الكود الخاص بك.

# --hints--

يجب أن تستخدم حلقة `do...while` لهذا التمرين.

```js
assert(__helpers.removeJSComments(code).match(/do/g));
```

يجب أن يساوي `myArray` قيمة `[10]`.

```js
assert.deepEqual(myArray, [10]);
```

يجب أن يساوي `i` قيمة `11`

```js
assert.equal(i, 11);
```

# --seed--

## --after-user-code--

```js
if(typeof myArray !== "undefined"){(function(){return myArray;})();}
```

## --seed-contents--

```js
// Setup
const myArray = [];
let i = 10;

// Only change code below this line
while (i < 5) {
  myArray.push(i);
  i++;
}
```

# --solutions--

```js
const myArray = [];
let i = 10;
do {
  myArray.push(i);
  i++;
} while (i < 5)
```
