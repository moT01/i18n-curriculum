---
id: 5a24c314108439a4d4036170
title: Crea un componente de estado
challengeType: 6
forumTopicId: 301391
dashedName: create-a-stateful-component
---

# --description--

One of the most important topics in React is `state`. State consists of any data your application needs to know about, that can change over time. You want your apps to respond to state changes and present an updated UI when necessary. React offers a nice solution for the state management of modern web applications.

Creas un estado en un componente de React declarando una propiedad `state` en la clase del componente en su `constructor`. Esto inicializa el componente con `state` cuando se crea. La propiedad `state` debe establecerse en un `object` de JavaScript. Declararlo se ve así:

```jsx
this.state = {

}
```

Tienes acceso al objeto `state` a lo largo de la vida de tu componente. Puedes actualizarlo, renderizarlo en tu interfaz de usuario y pasarlo como propiedades a componentes hijos. El objeto `state` puede ser tan complejo o simple como lo necesites. Ten en cuenta que debes crear un componente de clase heredando `React.Component` para crear un `state` como este.

# --instructions--

Hay un componente en el editor de código que está intentando renderizar una propiedad `firstName` desde su `state`. Sin embargo, no hay ningún `state` definido. Inicia el componente con `state` en el `constructor` y asigna tu nombre a la propiedad`firstName`.

# --hints--

`StatefulComponent` debe existir y renderizar.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    return mockedComponent.find('StatefulComponent').length === 1;
  })()
);
```

`StatefulComponent` debe renderizar un `div` y un elemento `h1`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    return (
      mockedComponent.find('div').length === 1 &&
      mockedComponent.find('h1').length === 1
    );
  })()
);
```

El estado de `StatefulComponent` debe iniciarse con la propiedad`firstName` establecida como un "string".

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    const initialState = mockedComponent.state();
    return (
      typeof initialState === 'object' && typeof initialState.firstName === 'string'
    );
  })()
);
```

La propiedad `firstName` en el estado `StatefulComponent` debe renderizar en el elemento `h1`.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(
      React.createElement(StatefulComponent)
    );
    const initialState = mockedComponent.state();
    return mockedComponent.find('h1').text() === initialState.firstName;
  })()
);
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<StatefulComponent />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    // Only change code below this line

    // Only change code above this line
  }
  render() {
    return (
      <div>
        <h1>{this.state.firstName}</h1>
      </div>
    );
  }
};
```

# --solutions--

```jsx
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      firstName: 'freeCodeCamp!'
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.firstName}</h1>
      </div>
    );
  }
};
```
