---
id: 5900f4f71000cf542c51000a
title: 'Problem 395: Pythagoras-Baum'
challengeType: 1
forumTopicId: 302060
dashedName: problem-395-pythagorean-tree
---

# --description--

Der Pythagoräische Baum ist ein Fraktal, das durch das folgende Verfahren erzeugt wird:

Beginne mit einem Einheitsquadrat. Dann nennt man eine der Seiten die Basis (in der Animation ist die untere Seite die Basis):

1. Befestige ein rechtwinkliges Dreieck an der Seite gegenüber der Basis, wobei die Hypotenuse mit dieser Seite übereinstimmt und die Seiten im Verhältnis 3-4-5 stehen. Beachte, dass die kleinere Seite des Dreiecks in Bezug auf die Basis auf der "rechten" Seite liegen muss (siehe Animation).
2. Befestige an jedem Schenkel des rechtwinkligen Dreiecks ein Quadrat, wobei eine seiner Seiten mit dem Schenkel zusammenfällt.
3. Wiederhole diesen Vorgang für beide Quadrate, wobei die Seiten, die das Dreieck berühren, als Basis dienen.

Nach einer unendlichen Anzahl von Iterationen ergibt sich der Pythagoras-Baum.

<img alt="Animation mit 8 Iterationen des Verfahrens" src="https://cdn.freecodecamp.org/curriculum/project-euler/pythagorean-tree.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Es lässt sich zeigen, dass es mindestens ein Rechteck gibt, dessen Seiten parallel zum größten Quadrat des Pythagoras-Baums verlaufen und das den Pythagoras-Baum vollständig umschließt.

Ermittle die kleinstmögliche Fläche für ein solches begrenzendes Rechteck und gebe deine Antwort auf 10 Dezimalstellen gerundet an.

# --hints--

`pythagoreanTree()` sollte `28.2453753155` zurückgeben.

```js
assert.strictEqual(pythagoreanTree(), 28.2453753155);
```

# --seed--

## --seed-contents--

```js
function pythagoreanTree() {

  return true;
}

pythagoreanTree();
```

# --solutions--

```js
// solution required
```
