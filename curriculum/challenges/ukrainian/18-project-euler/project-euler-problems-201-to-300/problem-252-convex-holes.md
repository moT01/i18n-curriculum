---
id: 5900f4691000cf542c50ff7b
title: 'Завдання 252: опуклі отвори'
challengeType: 1
forumTopicId: 301900
dashedName: problem-252-convex-holes
---

# --description--

Маючи множину точок на площині, визначимо опуклий отвір як опуклий багатокутник, що має вершини у будь-якій з даних точок та не містить жодної з даних точок в собі (до того ж інші дані точки можуть лежати на сторонах багатокутника).

Наприклад, на зображенні нижче маємо множину з 20 точок та декілька опуклих отворів. Опуклий отвір позначено червоним семикутником із площею 1049694.5 квадратних одиниць, що є найбільшою можливою площею опуклого отвору для даної множини точок.

<img alt="множина з 20 точок та опуклі отвори на площині" src="https://cdn.freecodecamp.org/curriculum/project-euler/convex-holes.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Для прикладу ми використали перші 20 точок ($T_{2k − 1}$, $T_{2k}$), за умови $k = 1, 2, \ldots, 20$, отриманих за допомогою генератора псевдовипадкових чисел:

$$\begin{align}   S_0 & = 290\\,797 \\\\
  S_{n+1} & = {S_n}^2 \\; \text{mod} \\; 50\\,515\\,093 \\\\ T_n & = (S_n \\; \text{mod} \\; 2000) − 1000 \end{align}$$

тобто (527, 144), (−488, 732), (−454, −947), …

Якою є максимальна площа опуклого отвору для множини, яка містить перші 500 точок у псевдовипадковій послідовності? Дайте відповідь, заокруглену до одного знаку після коми.

# --hints--

`convexHoles()` має повернути `104924`.

```js
assert.strictEqual(convexHoles(), 104924);
```

# --seed--

## --seed-contents--

```js
function convexHoles() {

  return true;
}

convexHoles();
```

# --solutions--

```js
// solution required
```
