---
id: 5a24c314108439a4d4036185
title: استخدم && لمزيد من تشرط متسق (Concise Conditional)
challengeType: 6
forumTopicId: 301413
dashedName: use--for-a-more-concise-conditional
---

# --description--

The `if/else` statements worked in the last challenge, but there's a more concise way to achieve the same result. Imagine that you are tracking several conditions in a component and you want different elements to render depending on each of these conditions. If you write a lot of `else if` statements to return slightly different UIs, you may repeat code which leaves room for error. Instead, you can use the `&&` logical operator to perform conditional logic in a more concise way. This is possible because you want to check if a condition is `true`, and if it is, return some markup. إليك مثال:

```jsx
{condition && <p>markup</p>}
```

إذا كان `condition` تكون `true`، سيتم إرجاع العلامة. إذا كان الشرط هو `false`، فإن العملية سوف تعود `false` فوراً بعد قياس `condition` وعدم إرجاع أي شيء. يمكنك تضمين هذه التعبيرات في JSX الخاص بك قاصدًا, وكتابة الشروط المتعددة (string multiple conditions) معاً بكتابة `&&` بعد كل واحدة منها. يتيح لك هذا التعامل مع المنطق الشرطي الأكثر تعقيداً في طريقة `render()` الخاصة بك دون تكرار الكثير من التعليمات البرمجية.

# --instructions--

حل المثال السابق مرة أخرى، لتقديد `h1` فقط إذا كان `display` بحالة `true`، ولكن استخدم `&&` المشغل المنطقي بدلاً من `if/else`.

# --hints--

`MyComponent` يجب أن يكون موجودا وينتج.

```js
assert(
  (function () {
    const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
    return mockedComponent.find('MyComponent').length;
  })()
);
```

عندما يتم تعيين `display` إلى `true`، و سوف ينتج `div`، و`button`, و `h1`.

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const state_1 = () => {
    mockedComponent.setState({ display: true });
    return waitForIt(() => mockedComponent);
  };
  const updated = await state_1();
  assert(
    updated.find('div').length === 1 &&
      updated.find('div').children().length === 2 &&
      updated.find('button').length === 1 &&
      updated.find('h1').length === 1
  );
};
```

عندما يتم تعيين `display` إلى `false`، يتم إنتاج `div` و `button` فقط.

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const state_1 = () => {
    mockedComponent.setState({ display: false });
    return waitForIt(() => mockedComponent);
  };
  const updated = await state_1();
  assert(
    updated.find('div').length === 1 &&
      updated.find('div').children().length === 1 &&
      updated.find('button').length === 1 &&
      updated.find('h1').length === 0
  );
};
```

يجب أن تستخدم طريقة (method) التقديم `&&` المشغل المنطقي (logical operator) للتحقق من `this.state.display`.

```js
(getUserInput) => assert(getUserInput('index').includes('&&'));
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
      display: true
    }
    this.toggleDisplay = this.toggleDisplay.bind(this);
  }
  toggleDisplay() {
    this.setState(state => ({
      display: !state.display
    }));
  }
  render() {
    // Change code below this line
    return (
       <div>
         <button onClick={this.toggleDisplay}>Toggle Display</button>
         <h1>Displayed!</h1>
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
      display: true
    }
 this.toggleDisplay = this.toggleDisplay.bind(this);
  }
  toggleDisplay() {
    this.setState(state => ({
      display: !state.display
    }));
  }
  render() {
    // Change code below this line
    return (
       <div>
         <button onClick={this.toggleDisplay}>Toggle Display</button>
         {this.state.display && <h1>Displayed!</h1>}
       </div>
    );
  }
};
```
