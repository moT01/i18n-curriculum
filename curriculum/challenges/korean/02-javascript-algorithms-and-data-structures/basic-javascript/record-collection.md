---
id: 56533eb9ac21ba0edf2244cf
title: 레코드 컬렉션 (Record Collection)
challengeType: 1
forumTopicId: 18261
dashedName: record-collection
---

# --description--

You are creating a function that aids in the maintenance of a musical album collection. The collection is organized as an object that contains multiple albums which are also objects. Each album is represented in the collection with a unique `id` as the property name. Within each album object, there are various properties describing information about the album. Not all albums have complete information.

`updateRecords` 함수는 다음 함수 매개변수로 표현된 4개의 인수를 받습니다.

-   `records` - an object containing several individual albums
-   `id` - a number representing a specific album in the `records` object
-   `prop` - a string representing the name of the album’s property to update
-   `value` - a string containing the information used to update the album’s property

함수에 전달된 객체를 아래의 규칙을 사용하여 수정하도록 이 함수를 완성하세요.

-   Your function must always return the entire `records` object.
-   만약 `value`가 빈 문자열이라면, 해당 앨범에서 주어진 `prop` 속성을 삭제하세요.
-   `prop`이 `tracks`이 아니고 `value`가 빈 문자열이 아니라면, 해당 앨범의 `prop`에 `value`를 할당하세요.
-   `prop`이 `tracks`이고 `value`가 빈 문자열이 아니며 앨범에 `tracks` 속성이 없다면, 빈 배열을 생성하고 `value`를 추가하세요.
-   prop이 `tracks`이고 `value`가 빈 문자열이 아니라면, 해당 앨범의 기존 `tracks` 배열 끝에 `value`를 추가하세요.

**참고:** 테스트를 위해 `recordCollection` 객체의 복사본이 사용됩니다. `recordCollection` 객체를 직접 수정하지 않아야 합니다.

# --hints--

`updateRecords(recordCollection, 5439, "artist", "ABBA")`를 실행한 후, `artist`는 문자열 `ABBA`가 되어야 합니다.

```js
assert(
  updateRecords(_recordCollection, 5439, 'artist', 'ABBA')[5439]['artist'] ===
    'ABBA'
);
```

`updateRecords(recordCollection, 5439, "tracks", "Take a Chance on Me")`를 실행한 후, `tracks`는 문자열 `Take a Chance on Me`를 마지막이자 유일한 요소로 가져야 합니다.

```js
assert(
  updateRecords(_recordCollection, 5439, 'tracks', 'Take a Chance on Me') &&
  _recordCollection[5439]['tracks'].length === 1 &&
  _recordCollection[5439]['tracks'].pop() === 'Take a Chance on Me'
);
```

`updateRecords(recordCollection, 2548, "artist", "")`를 실행한 후, `artist`는 설정되지 않아야 합니다.

```js
updateRecords(_recordCollection, 2548, 'artist', '');
assert(!_recordCollection[2548].hasOwnProperty('artist'));
```

`updateRecords(recordCollection, 1245, "tracks", "Addicted to Love")`를 실행한 후, `tracks`는 문자열 `Addicted to Love`를 마지막 요소로 가져야 합니다.

```js
assert(
  updateRecords(_recordCollection, 1245, 'tracks', 'Addicted to Love')[1245][
    'tracks'
  ].pop() === 'Addicted to Love'
);
```

`updateRecords(recordCollection, 2468, "tracks", "Free")`를 실행한 후, `tracks`는 문자열 `1999`를 첫 번째 요소로 가져야 합니다.

```js
assert(
  updateRecords(_recordCollection, 2468, 'tracks', 'Free')[2468][
    'tracks'
  ][0] === '1999'
);
```

`updateRecords(recordCollection, 2548, "tracks", "")`를 실행한 후, `tracks`는 설정되지 않아야 합니다.

```js
updateRecords(_recordCollection, 2548, 'tracks', '');
assert(!_recordCollection[2548].hasOwnProperty('tracks'));
```

`updateRecords(recordCollection, 1245, "albumTitle", "Riptide")`를 실행한 후, `albumTitle`은 문자열 `Riptide`가 되어야 합니다.

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
