---
id: 56bbb991ad1ed5201cd392cf
title: كتابة JavaScript قابلة لإعادة الاستخدام بواسطة الوظائف (Functions)
challengeType: 1
videoUrl: 'https://scrimba.com/c/cL6dqfy'
forumTopicId: 18378
dashedName: write-reusable-javascript-with-functions
---

# --description--

In JavaScript, we can divide up our code into reusable parts called <dfn>functions</dfn>.

إليك مثال لوظيفة:

```js
function functionName() {
  console.log("Hello World");
}
```

يمكنك تنفيذ أو <dfn>تفعيل</dfn> هذه الوظيفة باستخدام اسمها متبوعا بقوسين، هكذا: `functionName();`. في كل مرة تفعَّل الوظيفة، ستطبع الرسالة `Hello World` في الكونسول (console). سيتم تنفيذ الكود بين الأقواس المقرونة في كل مرة تفعَّل الوظيفة.

# --instructions--

<ol>
  <li>
    Create a function called <code>reusableFunction</code> which prints the string <code>Hi World</code> to the dev console.
  </li>
  <li>
    فعِّل الوظيفة.
  </li>
</ol>

# --hints--

يجب أن تكون `reusableFunction` وظيفة.

```js
assert(typeof reusableFunction === 'function');
```

إذا تم تفعيل `reusableFunction`، فيجب طباعة مقطع `Hi World` في الكونسول.

```js
assert(testConsole());
```

يجب عليك تفعيل `reusableFunction` بمجرد تعريفها.

```js
const functionStr = reusableFunction && __helpers.removeWhiteSpace(reusableFunction.toString());
const codeWithoutFunction = __helpers.removeWhiteSpace(__helpers.removeJSComments(code)).replace(/reusableFunction\(\)\{/g, '');
assert(/reusableFunction\(\)/.test(codeWithoutFunction));
```

# --seed--

## --after-user-code--

```js

function testConsole() {
  var logOutput = "";
  var originalConsole = console;
  var nativeLog = console.log;
  var hiWorldWasLogged = false;
  console.log = function (message) {
    if(message === 'Hi World')  {
      console.warn(message)
      hiWorldWasLogged = true;
    }
    if(message && message.trim) logOutput = message.trim();
    if(nativeLog.apply) {
      nativeLog.apply(originalConsole, arguments);
    } else {
      var nativeMsg = Array.prototype.slice.apply(arguments).join(' ');
      nativeLog(nativeMsg);
    }
  };
  reusableFunction();
  console.log = nativeLog;
  return hiWorldWasLogged;
}

```

## --seed-contents--

```js

```

# --solutions--

```js
function reusableFunction() {
  console.log("Hi World");
}
reusableFunction();
```
