---
id: 5a24c314108439a4d4036150
title: Gestire un'azione nello store
challengeType: 6
forumTopicId: 301444
dashedName: handle-an-action-in-the-store
---

# --description--

After an action is created and dispatched, the Redux store needs to know how to respond to that action. This is the job of a `reducer` function. Reducers in Redux are responsible for the state modifications that take place in response to actions. A `reducer` takes `state` and `action` as arguments, and it always returns a new `state`. It is important to see that this is the **only** role of the reducer. It has no side effects — it never calls an API endpoint and it never has any hidden surprises. The reducer is simply a pure function that takes state and action, then returns new state.

Un altro principio chiave in Redux è che lo `state` è di sola lettura. In altre parole, la funzione `reducer` deve **sempre** restituire una nuova copia dello `state` e non modificare mai direttamente lo state. Redux non forza l'immutabilità dello stato, tuttavia sei responsabile di applicarlo nel codice delle tue funzioni reducer. Nelle prossime sfide farai pratica con questo.

# --instructions--

L'editor di codice contiene l'esempio precedente e l'inizio di una funzione `reducer` pronti per te. Compila il corpo della funzione `reducer` in modo che se riceve un'azione di tipo `'LOGIN'` restituisca un oggetto stato con `login` impostato a `true`. Altrimenti, restituisce lo `state` attuale. Nota che lo `state` corrente e l'`action` inviata sono passati al reducer, in modo da poter accedere direttamente al tipo di azione con `action.type`.

# --hints--

Chiamare la funzione `loginAction` dovrebbe restituire un oggetto con proprietà type impostata sulla stringa `LOGIN`.

```js
assert(loginAction().type === 'LOGIN');
```

Lo store dovrebbe essere inizializzato con un oggetto con proprietà `login` impostata su `false`.

```js
assert(store.getState().login === false);
```

Inviare `loginAction` dovrebbe aggiornare la proprietà `login` nello stato dello store a `true`.

```js
assert(
  (function () {
    const initialState = store.getState();
    store.dispatch(loginAction());
    const afterState = store.getState();
    return initialState.login === false && afterState.login === true;
  })()
);
```

Se l'azione non è di tipo `LOGIN`, lo store dovrebbe restituire lo stato corrente.

```js
assert(
  (function () {
    store.dispatch({ type: '__TEST__ACTION__' });
    let afterTest = store.getState();
    return typeof afterTest === 'object' && afterTest.hasOwnProperty('login');
  })()
);
```

# --seed--

## --seed-contents--

```js
const defaultState = {
  login: false
};

const reducer = (state = defaultState, action) => {
  // Change code below this line

  // Change code above this line
};

const store = Redux.createStore(reducer);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};
```

# --solutions--

```js
const defaultState = {
  login: false
};

const reducer = (state = defaultState, action) => {

  if (action.type === 'LOGIN') {
    return {login: true}
  }

  else {
    return state
  }

};

const store = Redux.createStore(reducer);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};
```
