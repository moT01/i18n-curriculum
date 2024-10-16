---
id: 5a24c314108439a4d4036176
title: استخدام الحالة (State) لتبديل العنصر
challengeType: 6
forumTopicId: 301421
dashedName: use-state-to-toggle-an-element
---

# --description--

Sometimes you might need to know the previous state when updating the state. However, state updates may be asynchronous - this means React may batch multiple `setState()` calls into a single update. This means you can't rely on the previous value of `this.state` or `this.props` when calculating the next value. So, you should not use code like this:

```jsx
this.setState({
  counter: this.state.counter + this.props.increment
});
```

بدلاً من ذلك، يجب عليك تمرير وظيفة `setState` تسمح لك بالوصول إلى الحالة (state) ومِيزات (props). استخدام وظيفة (function) مع `setState` يضمن لك العمل مع أكثر القيم حداثة من الحالة (state) والمِيزات (props). وهذا يعني أنه ينبغي إعادة كتابة ما ورد أعلاه على النحو التالي:

```jsx
this.setState((state, props) => ({
  counter: state.counter + props.increment
}));
```

يمكنك أيضًا استخدام نموذج (form) دون `props` إذا كنت بحاجة فقط إلى `state`:

```jsx
this.setState(state => ({
  counter: state.counter + 1
}));
```

لاحظ أنه يجب عليك تغليف object literal بين قوسين، وإلا فإن JavaScript تعتقد أنها كتلة من التعليمات البرمجية.

# --instructions--

`MyComponent` لها خاصية `visibility` التي تم تهيئتها إلى `false`. تنتج طريقة العرض طريقة عرض واحدة إذا كانت قيمة `visibility` صحيحة، وعرضًا مختلفًا إذا كانت خاطئة (false).

حاليا، لا توجد طريقة لتحديث خاصية `visibility` في `state` المكون (component). يجب أن تبديل القيمة ذهابا وإيابا بين الحقيقة (true) والخاطئة (false). هناك معالج ضغط على الزر الذي يشغل طريقة فئة تسمى `toggleVisibility()`. مرر الوظيفة (function) إلى `setState` لتعريف هذه الطريقة (method) بحيث تبديل `state` بقيمة `visibility` إلى القيمة المضادة عند تشغيل الطريقة (method). إذا كان `visibility` يكون `false`، فالطريقة تغيره إلى `true`، والعكس كذلك.

وأخيراً، انقر على الزر لرؤية العرض المشروط (conditional rendering) للمكون استناداً إلى `state`.

**تلميح:** لا تنس أن تربط الكلمة `this` بالطريقة في `constructor`!

# --hints--

يجب أن ينتج `MyComponent` عنصر `div` الذي يحتوي علامة `button`.

```js
assert.strictEqual(
  Enzyme.mount(React.createElement(MyComponent)).find('div').find('button')
    .length,
  1
);
```

يجب أن تَبدء حالة (state) في `MyComponent` بخاصية `visibility` يرجع حالة `false`.

```js
assert.strictEqual(
  Enzyme.mount(React.createElement(MyComponent)).state('visibility'),
  false
);
```

Clicking the button element should toggle the `visibility` property in state between `true` and `false` and conditionally render the `h1` element.

```js
(() => {
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const first = () => {
    mockedComponent.setState({ visibility: false });
    return mockedComponent.state('visibility');
  };
  const second = () => {
    mockedComponent.find('button').simulate('click');
    return mockedComponent.state('visibility') && mockedComponent.find('h1').exists();
  };
  const third = () => {
    mockedComponent.find('button').simulate('click');
    return mockedComponent.state('visibility') && mockedComponent.find('h1').exists();
  };
  const firstValue = first();
  const secondValue = second();
  const thirdValue = third();
  assert(!firstValue && secondValue && !thirdValue);
})();
```

يجب تمرير وظيفة مجهولة (anonymous function) إلى `setState`.

```js
const paramRegex = '[a-zA-Z$_]\\w*(,[a-zA-Z$_]\\w*)?';
assert(
  new RegExp(
    'this\\.setState\\((function\\(' +
      paramRegex +
      '\\){|([a-zA-Z$_]\\w*|\\(' +
      paramRegex +
      '\\))=>)'
  ).test(__helpers.removeWhiteSpace(code))
);
```

يجب عدم استخدام `this` داخل `setState`

```js
assert(!/this\.setState\([^}]*this/.test(code));
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<MyComponent />, document.getElementById('root'));
```

## --seed-contents--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      visibility: false
    };
    // Change code below this line

    // Change code above this line
  }
  // Change code below this line

  // Change code above this line
  render() {
    if (this.state.visibility) {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
          <h1>Now you see me!</h1>
        </div>
      );
    } else {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
        </div>
      );
    }
  }
}
```

# --solutions--

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      visibility: false
    };
    this.toggleVisibility = this.toggleVisibility.bind(this);
  }
  toggleVisibility() {
    this.setState(state => ({
      visibility: !state.visibility
    }));
  }
  render() {
    if (this.state.visibility) {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
          <h1>Now you see me!</h1>
        </div>
      );
    } else {
      return (
        <div>
          <button onClick={this.toggleVisibility}>Click Me</button>
        </div>
      );
    }
  }
}
```
