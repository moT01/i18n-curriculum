---
id: 587d7b8c367417b2b2512b58
title: Create an Export Fallback with export default
challengeType: 1
forumTopicId: 301199
dashedName: create-an-export-fallback-with-export-default
---

# --description--

In the `export` lesson, you learned about the syntax referred to as a <dfn>named export</dfn>. This allowed you to make multiple functions and variables available for use in other files.

هناك بنية `export` أخرى تحتاج إلى معرفتها، والمعروفة باسم <dfn>export default</dfn>. عادة سوف تستخدم هذه الجملة إذا تم تصدير قيمة واحدة فقط من ملف. يتم استخدامه أيضا لإنشاء قيمة احتياطية لملف أو module.

فيما يلي أمثلة تستخدم `export default`:

```js
export default function add(x, y) {
  return x + y;
}

export default function(x, y) {
  return x + y;
}
```

الأول هو named function، والثاني هو anonymous function.

لما كان `export default` يستخدم لإعلان القيمة الاحتياطية لـ module أو ملف، يمكن أن يكون لديك قيمة واحدة فقط هي الـ default export في كل module أو ملف. بالإضافة إلى ذلك، لا يمكنك استخدام `export default` مع `var` أو `let` أو `const`

# --instructions--

الوظيفة التالية يجب أن تكون القيمة الاحتياطية للـ module. الرجاء إضافة الكود اللازم للقيام بذلك.

# --hints--

يجب أن يستخدم الكود الخاص بك `export` احتياطيًا.

```js
assert(
  __helpers.removeJSComments(code).match(
    /export\s+default\s+function(\s+subtract\s*|\s*)\(\s*x,\s*y\s*\)\s*{/g
  )
);
```

# --seed--

## --seed-contents--

```js
function subtract(x, y) {
  return x - y;
}
```

# --solutions--

```js
export default function subtract(x, y) {
  return x - y;
}
```
