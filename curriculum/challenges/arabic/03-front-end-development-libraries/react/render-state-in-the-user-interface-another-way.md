---
id: 5a24c314108439a4d4036172
title: أنتاج الحالة (State) في واجهة المستخدم (User Interface) بطريقة أخرى
challengeType: 6
forumTopicId: 301408
dashedName: render-state-in-the-user-interface-another-way
---

# --description--

There is another way to access `state` in a component. In the `render()` method, before the `return` statement, you can write JavaScript directly. For example, you could declare functions, access data from `state` or `props`, perform computations on this data, and so on. Then, you can assign any data to variables, which you have access to in the `return` statement.

# --instructions--

في طريقة التقديم `MyComponent`، حدد `const` باسم `name` وعيّنه يساوي قيمة الاسم في `state` المكون. لأنه يمكنك كتابة JavaScript قاصدًا في هذا الجزء من التعليمات البرمجية، ليس عليك تغلفه هذا المرجع بأقواس منحنية (curly braces).

بعد ذلك، في بيان الإرجاع، أنتج هذه القيمة في وسم `h1` باستخدام المتغير `name`. تذكر، تحتاج إلى استخدام جملة JSX (الأقواس المنحنية في JavaScript) في بيان أنتاج (return statement).

# --hints--

`MyComponent` يجب أن يكون لديه هُوِيَّة `name` بقيمة `freeCodeCamp` مخزنة في الحالة (state).

```js
assert(
  Enzyme.mount(React.createElement(MyComponent)).state('name') ===
    'freeCodeCamp'
);
```

`MyComponent` يجب أن يجعل عنصر `h1` عنوان مغلف في `div` واحد.

```js
assert(
  /<div><h1>.*<\/h1><\/div>/.test(
    Enzyme.mount(React.createElement(MyComponent)).html()
  )
);
```

يجب أن تتضمن العلامة `h1` المنشئة مرجع `{name}`.

```js
(getUserInput) =>
  assert(/<h1>\n*\s*\{\s*name\s*\}\s*\n*<\/h1>/.test(getUserInput('index')));
```

يجب أن يحتوي عنصر العنوان `h1` المُنتج على النص المقدم من حالة المكون (component's state).

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const first = () => {
    mockedComponent.setState({ name: 'TestName' });
    return waitForIt(() => mockedComponent.html());
  };
  const firstValue = await first();
  assert(firstValue === '<div><h1>TestName</h1></div>');
};
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<MyComponent />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // Change code below this line

    // Change code above this line
    return (
      <div>
        { /* Change code below this line */ }

        { /* Change code above this line */ }
      </div>
    );
  }
};
```

# --solutions--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'freeCodeCamp'
    }
  }
  render() {
    // Change code below this line
    const name = this.state.name;
    // Change code above this line
    return (
      <div>
        { /* Change code below this line */ }
        <h1>{name}</h1>
        { /* Change code above this line */ }
      </div>
    );
  }
};
```
