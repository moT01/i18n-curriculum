---
id: 56533eb9ac21ba0edf2244cf
title: Exibir uma coleção de discos
challengeType: 1
forumTopicId: 18261
dashedName: record-collection
---

# --description--

You are creating a function that aids in the maintenance of a musical album collection. The collection is organized as an object that contains multiple albums which are also objects. Each album is represented in the collection with a unique `id` as the property name. Within each album object, there are various properties describing information about the album. Not all albums have complete information.

A função `updateRecords` recebe 4 argumentos representados pelos seguintes parâmetros de função:

-   `records` - an object containing several individual albums
-   `id` - a number representing a specific album in the `records` object
-   `prop` - a string representing the name of the album’s property to update
-   `value` - a string containing the information used to update the album’s property

Complete a função usando as regras abaixo para modificar o objeto passado para a função.

-   Your function must always return the entire `records` object.
-   Se `value` for uma string vazia, remova a propriedade `prop` recebida do álbum.
-   Se `prop` não for `tracks` e `value` não for uma string vazia, atribua `value` à `prop` daquele álbum.
-   Se `prop` for `tracks` e `value` não for uma string vazia e se o álbum não tiver uma propriedade `tracks`, crie um array vazio e adicione `value` a ele.
-   Se prop for `tracks` e `value` não for uma string vazia, adicione `value` ao final do array existente de `tracks` do álbum.

**Observação:** uma cópia do objeto `recordCollection` é usada para testes. Você não deve modificar diretamente o objeto `recordCollection`.

# --hints--

Após `updateRecords(recordCollection, 5439, "artist", "ABBA")`, `artist` deve ter a string `ABBA`.

```js
assert(
  updateRecords(_recordCollection, 5439, 'artist', 'ABBA')[5439]['artist'] ===
    'ABBA'
);
```

Após `updateRecords(recordCollection, 5439, "tracks", "Take a Chance on Me")`, `tracks` deve ter a string `Take a Chance on Me` como o último e único elemento.

```js
assert(
  updateRecords(_recordCollection, 5439, 'tracks', 'Take a Chance on Me') &&
  _recordCollection[5439]['tracks'].length === 1 &&
  _recordCollection[5439]['tracks'].pop() === 'Take a Chance on Me'
);
```

Após `updateRecords(recordCollection, 2548, "artist", "")`, `artist` não deve ser definido.

```js
updateRecords(_recordCollection, 2548, 'artist', '');
assert(!_recordCollection[2548].hasOwnProperty('artist'));
```

Após `updateRecords(recordCollection, 1245, "tracks", "Addicted to Love")`, `tracks` deve ter a string `Addicted to Love` como o último elemento.

```js
assert(
  updateRecords(_recordCollection, 1245, 'tracks', 'Addicted to Love')[1245][
    'tracks'
  ].pop() === 'Addicted to Love'
);
```

Após `updateRecords(recordCollection, 2468, "tracks", "Free")`, `tracks` deve ter a string `1999` como o último elemento.

```js
assert(
  updateRecords(_recordCollection, 2468, 'tracks', 'Free')[2468][
    'tracks'
  ][0] === '1999'
);
```

Após `updateRecords(recordCollection, 2548, "tracks", "")`, `tracks` não deve ser definido.

```js
updateRecords(_recordCollection, 2548, 'tracks', '');
assert(!_recordCollection[2548].hasOwnProperty('tracks'));
```

Após `updateRecords(recordCollection, 1245, "albumTitle", "Riptide")`, `albumTitle` deve ser a string `Riptide`.

```js
assert(
  updateRecords(_recordCollection, 1245, 'albumTitle', 'Riptide')[1245][
    'albumTitle'
  ] === 'Riptide'
);
```

# --seed--

## --before-user-code--

```js
const _recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};
```

## --seed-contents--

```js
// Setup
const recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};

// Only change code below this line
function updateRecords(records, id, prop, value) {
  return records;
}

updateRecords(recordCollection, 5439, 'artist', 'ABBA');
```

# --solutions--

```js
const recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};

// Only change code below this line
function updateRecords(records, id, prop, value) {
  if (value === '') delete records[id][prop];
  else if (prop === 'tracks') {
    records[id][prop] = records[id][prop] || [];
    records[id][prop].push(value);
  } else {
    records[id][prop] = value;
  }

  return records;
}
```
