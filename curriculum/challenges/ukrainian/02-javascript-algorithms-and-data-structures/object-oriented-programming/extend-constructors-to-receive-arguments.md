---
id: 587d7dae367417b2b2512b79
title: Розширення конструкторів для отримання аргументів
challengeType: 1
forumTopicId: 18235
dashedName: extend-constructors-to-receive-arguments
---

# --description--

The `Bird` and `Dog` constructors from the last challenge worked well. However, notice that all `Birds` that are created with the `Bird` constructor are automatically named Albert, are blue in color, and have two legs. What if you want birds with different values for name and color? It's possible to change the properties of each bird manually but that would be a lot of work:

```js
let swan = new Bird();
swan.name = "Carlos";
swan.color = "white";
```

Припустимо, ви писали програму для відстеження сотень чи навіть тисяч різних пташок у пташнику. Створення всіх пташок займе багато часу, а потім ще потрібно змінити значення властивостей. Щоб легше створювати різні об’єкти `Bird`, ви можете спроєктувати конструктор для прийняття параметрів:

```js
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```

Потім передайте значення як аргументи, щоб визначити кожну унікальну пташку в конструкторі `Bird`: `let cardinal = new Bird("Bruce", "red");`. Ви отримаєте новий екземпляр `Bird` із властивостями `name` та `color` з відповідними значеннями `Bruce` та `red`. Властивість `numLegs` досі має значення 2. `cardinal` має такі властивості:

```js
cardinal.name
cardinal.color
cardinal.numLegs
```

Конструктор є більш гнучким. Тепер можна визначити властивості для кожної пташки під час її створення, що є однією з причин, чому конструктори JavaScript такі корисні. Вони групують об’єкти на основі спільних характеристик і поведінки та визначають план, який автоматизує їхнє створення.

# --instructions--

Створіть ще один конструктор `Dog`. Цього разу налаштуйте його так, щоб він приймав параметри `name` та `color`, і встановіть властивість `numLegs` на 4. Потім створіть новий `Dog`, збережений у змінній `terrier`. Передайте два рядки як аргументи до властивостей `name` та `color`.

# --hints--

`Dog` має отримати аргумент для `name`.

```js
assert(new Dog('Clifford').name === 'Clifford');
```

`Dog` має отримати аргумент для `color`.

```js
assert(new Dog('Clifford', 'yellow').color === 'yellow');
```

`Dog` повинен мати властивість `numLegs` зі значенням 4.

```js
assert(new Dog('Clifford').numLegs === 4);
```

Створіть `terrier` за допомогою конструктора `Dog`.

```js
assert(terrier instanceof Dog);
```

# --seed--

## --seed-contents--

```js
function Dog() {

}
```

# --solutions--

```js
function Dog (name, color) {
  this.numLegs = 4;
  this.name = name;
  this.color = color;
}

const terrier = new Dog();
```
