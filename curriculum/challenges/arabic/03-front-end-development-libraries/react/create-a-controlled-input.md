---
id: 5a24c314108439a4d4036178
title: إنشاء أدخال المتحكم فيه (Controlled Form)
challengeType: 6
forumTopicId: 301385
dashedName: create-a-controlled-input
---

# --description--

Your application may have more complex interactions between `state` and the rendered UI. For example, form control elements for text input, such as `input` and `textarea`, maintain their own state in the DOM as the user types. With React, you can move this mutable state into a React component's `state`. The user's input becomes part of the application `state`, so React controls the value of that input field. Typically, if you have React components with input fields the user can type into, it will be a controlled input form.

# --instructions--

يحتوي محرر التعليمات البرمجية على الهيكل العظمي لمكون يسمى `ControlledInput` لإنشاء عنصر `input` المتحكم بيه. تم فعلًا تهيئة `state` للمكون (component) مع خاصية (property) تسمى `input` التي تحتوي على مقطع نصي (string) فارغة. هذه القيمة تمثل نوع النص المستخدم في حقل `input`.

أولا، إنشاء طريقة تسمى `handleChange()` تحتوي على وسيط يسمى `event`. عندما يتم تسمية الطريقة، فإنها تتلقى كائن `event` يحتوي على سلسلة من النص من عنصر `input`. يمكنك الوصول إلى هذه السلسلة باستخدام `event.target.value` داخل الطريقة. حديث خاصية (property) تسمى `input` في `state` للمكون (component) مع هذا المقطع النصي (string) الجديدة.

في طريقة `render`، أنشئ عنصر `input` فوق علامة `h4`. أضف سمة (attribute) تسمى `value` تساوي خاصية (property) تسمى `input` في `state` للمكون (component). Then add an `onChange` property set to the `handleChange()` event handler method.

عندما تكتب في صندوق الإدخال (input)، يتم معالجة هذا النص بواسطة طريقة (method) تسمى `handleChange()`، تُعيين كخاصية (property) تسمى `input` في `state` المحلية، وتم أنتاجها كقيمة في صندوق `input` على الصفحة. تكون `state` المكون (component) المصدر الوحيد للحقيقة (single source of truth) فيما يتعلق ببيانات الإدخال (input).

أخيرا وليس آخرا، لا تنس أن تضيف الارتباطات اللازمة في البناء (constructor).

# --hints--

`ControlledInput` يجب أن يعيد عنصر `div` الذي يحتوي على علامات `input` و `p`.

```js
assert(
  Enzyme.mount(React.createElement(ControlledInput))
    .find('div')
    .children()
    .find('input').length === 1 &&
    Enzyme.mount(React.createElement(ControlledInput))
      .find('div')
      .children()
      .find('p').length === 1
);
```

يجب أن تهيئ حالة (state) في `ControlledInput` خاصية (property) تسمى `input` بقيمة مقطع فارغ (string).

```js
assert.strictEqual(
  Enzyme.mount(React.createElement(ControlledInput)).state('input'),
  ''
);
```

يجب أن تحديث الحالة (state) عند الكتابة في عنصر الإدخال (input) وتحديث قيمة الإدخال (input)، و يجب أن يجعل عنصر `p` هذه الحالة (state) كما تكتب.

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(ControlledInput));
  const _1 = () => {
    mockedComponent.setState({ input: '' });
    return waitForIt(() => mockedComponent.state('input'));
  };
  const _2 = () => {
    mockedComponent
      .find('input')
      .simulate('change', { target: { value: 'TestInput' } });
    return waitForIt(() => ({
      state: mockedComponent.state('input'),
      text: mockedComponent.find('p').text(),
      inputVal: mockedComponent.find('input').props().value
    }));
  };
  const before = await _1();
  const after = await _2();
  assert(
    before === '' &&
      after.state === 'TestInput' &&
      after.text === 'TestInput' &&
      after.inputVal === 'TestInput'
  );
};
```

# --seed--

## --after-user-code--

```jsx
ReactDOM.render(<ControlledInput />, document.getElementById('root'))
```

## --seed-contents--

```jsx
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    // Change code below this line

    // Change code above this line
  }
  // Change code below this line

  // Change code above this line
  render() {
    return (
      <div>
        { /* Change code below this line */}

        { /* Change code above this line */}
        <h4>Controlled Input:</h4>
        <p>{this.state.input}</p>
      </div>
    );
  }
};
```

# --solutions--

```jsx
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(event) {
    this.setState({
      input: event.target.value
    });
  }
  render() {
    return (
      <div>
        <input
          value={this.state.input}
          onChange={this.handleChange} />
        <h4>Controlled Input:</h4>

        <p>{this.state.input}</p>
      </div>
    );
  }
};
```
