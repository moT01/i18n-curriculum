---
id: 587d7b8c367417b2b2512b54
title: استخدام الـ getters والـ setters للتحكم في الوصول إلى الكائن
challengeType: 1
forumTopicId: 301220
dashedName: use-getters-and-setters-to-control-access-to-an-object
---

# --description--

You can obtain values from an object and set the value of a property within an object.

هذه تسمى تقليديا بـ <dfn>getters</dfn> و <dfn>setters</dfn>.

الغرض من وظائف جالب (Getter) هو ببساطة أنتاج قيمة المتغير الخاص (private) لكائن ما إلى المستخدم دون الوصول قاصدًا إلى المتغير الخاص.

الغرض من وظائف محدد (Setter) هو ببساطة تعيين قيمة المتغير الخاص لكائن ما استناداً إلى القيمة التي تمرر إلى وظيفة محدد (setter). قد يتضمن هذا التغيير عمليات حسابية، أو حتى الكتابة فوق القيمة السابقة بالكامل.

```js
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer() {
    return this._author;
  }
  // setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}
const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);
```

ستعرض وحدة التحكم السلسلتين strings باسم `anonymous` و `newAuthor`.

لاحظ الصيغة المستخدمة لاستدعاء getter و setter. حتى أنها لا تشبه الوظائف (functions) العادية. تعتبر الـ Getters و Setters مهمة لأنها تخفي تفاصيل التنفيذ الداخلية.

**ملاحظة:** من المألوف أن يسبق اسم المتغير الخاص برمز underscore هيئته (`_`). ومع ذلك، فإن الرمز نفسه لا يجعل المتغير خاصًا.

# --instructions--

استخدم كلمة `class` لإنشاء فئة `Thermostat`. يقبل `constructor` درجة حرارة فهرنهايت (Fahrenheit).

In the class, create a `getter` to obtain the temperature in Celsius and a `setter` that accepts a temperature in Celsius.

تذكر أن `C = 5/9 * (F - 32)` و `F = C * 9.0 / 5 + 32`، حيث `F` هي قيمة درجة الحرارة بالفهرنهايت، و `C` هي قيمة درجة الحرارة نفسها بالدرجة المئوية.

**ملاحظة:** عند تنفيذ هذا، فسوف تتبع درجة الحرارة داخل الفئة في مقياس واحد، إما فهرنهايت أو مئوية.

هذه هي قوة الـ setter و getter. أنت تقوم بإنشاء API لمستخدم آخر، يمكنه الحصول على النتيجة الصحيحة بغض النظر عن أي واحد تتبعه.

بمعنى آخر، أنت تجرد تفاصيل التنفيذ من المستخدم.

# --hints--

يجب أن يكون `Thermostat` بنوع `class` مع طريقة `constructor` محددة.

```js
assert.isFunction(Thermostat);
assert.isFunction(Thermostat?.constructor);
```

The `class` keyword should be used.

```js
assert.match(code, /class/);
```

`Thermostat` يجب أن يتم انشاء مثيل له.

```js
const _t = new Thermostat(122);
assert.isObject(_t);
```

عند إنشاء مثيل بقيمة فهرنهايت، يجب أن يضبط `Thermostat` درجة الحرارة الصحيحة `temperature`.

```js
const _t = new Thermostat(122);
assert.strictEqual(_t?.temperature, 50);
```

يجب تعريف `getter`.

```js
const _desc = Object.getOwnPropertyDescriptor(Thermostat.prototype, 'temperature');
assert.isFunction(_desc?.get);
```

يجب تعريف `setter`.

```js
const _desc = Object.getOwnPropertyDescriptor(Thermostat.prototype, 'temperature');
assert.isFunction(_desc?.set);
```

استدعاء `setter` مع قيمة مئوية يجب أن تحدد `temperature`.

```js
const _t = new Thermostat(32);
_t.temperature = 26;
const _u = new Thermostat(32);
_u.temperature = 50;
assert.approximately(_t.temperature, 26, 0.1);
assert.approximately(_u.temperature, 50, 0.1);
```

# --seed--

## --seed-contents--

```js
// Only change code below this line

// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```

# --solutions--

```js
class Thermostat {
  constructor(fahrenheit) {
    this._tempInCelsius = 5/9 * (fahrenheit - 32);
  }
  get temperature(){
    return this._tempInCelsius;
  }
  set temperature(newTemp){
    this._tempInCelsius = newTemp;
  }
}

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```
