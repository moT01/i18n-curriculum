---
id: 5a24c314108439a4d403617e
title: 이벤트 리스너 추가하기
challengeType: 6
forumTopicId: 301377
dashedName: add-event-listeners
---

# --description--

The `componentDidMount()` method is also the best place to attach any event listeners you need to add for specific functionality. React provides a synthetic event system which wraps the native event system present in browsers. This means that the synthetic event system behaves exactly the same regardless of the user's browser - even if the native events may behave differently between different browsers.

이미 합성 이벤트 핸들러를 사용하고 계실 겁니다. `onClick()`도 그 중 하나입니다. 리액트 합성 이벤트 시스템은, DOM 엘리먼트에서 관리하게 될 대부분의 상호 작용에 적합합니다. 하지만 이벤트 핸들러를 document 혹은 window 객체에 연결하고 싶으면, 직접 연결해줘야 합니다.

# --instructions--

`componentDidMount()`에 `keydown` 이벤트를 위한 리스너를 연결하고, 콜백으로 `handleKeyPress()`를 실행하게 해보세요. 첫 번째 인자로 이벤트를 갖고, 두 번째로는 콜백을 갖는 `document.addEventListener()`를 사용할 수 있습니다.

그런 다음 `componentWillUnmount()`에서 위의 이벤트 리스너를 제거해주세요. `document.removeEventListener()`에 동일한 인자들을 넣어주면 됩니다. 이 라이프사이클 메서드를 이용해서 리액트 컴포넌트가 언마운트되거나 없어질 때 정리해주는 것이 좋습니다. 이벤트 리스너를 제거해주는 것이 정리 작업의 한 예시입니다.

# --hints--

`MyComponent`는 `h1` 태그를 감싼 `div` 엘리먼트를 반환해야 합니다.

```js
assert(
  (() => {
    const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
    return mockedComponent.find('div').children().find('h1').length === 1;
  })()
);
```

`keydown` 리스너는 `componentDidMount` 안에서 document에 연결되어야 합니다.

```js
assert(
  (() => {
    const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
    const didMountString = mockedComponent
      .instance()
      .componentDidMount.toString();
    return new RegExp(
      'document.addEventListener(.|\n|\r)+keydown(.|\n|\r)+this.handleKeyPress'
    ).test(didMountString);
  })()
);
```

`keydown` 리스너는 `componentWillUnmount`에서 document에서 제거되어야 합니다.

```js
assert(
  (() => {
    const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
    const willUnmountString = mockedComponent
      .instance()
      .componentWillUnmount.toString();
    return new RegExp(
      'document.removeEventListener(.|\n|\r)+keydown(.|\n|\r)+this.handleKeyPress'
    ).test(willUnmountString);
  })()
);
```

컴포넌트가 DOM에 올려졌을 때(mount), `엔터`를 누르면 상태가 업데이트 되어야 하고, `h1` 태그에 렌더링 되어야 합니다.

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const beforeState = mockedComponent.state('message');
  const beforeText = mockedComponent.find('h1').text();
  const pressEnterKey = () => {
    mockedComponent.instance().handleKeyPress({ keyCode: 13 });
    return waitForIt(() => {
      mockedComponent.update();
      return {
        state: mockedComponent.state('message'),
        text: mockedComponent.find('h1').text()
      };
    });
  };
  const afterKeyPress = await pressEnterKey();
  assert(
    beforeState !== afterKeyPress.state && beforeText !== afterKeyPress.text
  );
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
      message: ''
    };
    this.handleEnter = this.handleEnter.bind(this);
    this.handleKeyPress = this.handleKeyPress.bind(this);
  }
  // Change code below this line
  componentDidMount() {

  }
  componentWillUnmount() {

  }
  // Change code above this line
  handleEnter() {
    this.setState((state) => ({
      message: state.message + 'You pressed the enter key! '
    }));
  }
  handleKeyPress(event) {
    if (event.keyCode === 13) {
      this.handleEnter();
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
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
      message: ''
    };
    this.handleKeyPress = this.handleKeyPress.bind(this);
    this.handleEnter = this.handleEnter.bind(this);  }
  componentDidMount() {
    // Change code below this line
    document.addEventListener('keydown', this.handleKeyPress);
    // Change code above this line
  }
  componentWillUnmount() {
    // Change code below this line
    document.removeEventListener('keydown', this.handleKeyPress);
    // Change code above this line
  }
  handleEnter() {
    this.setState((state) => ({
      message: state.message + 'You pressed the enter key! '
    }));
  }
  handleKeyPress(event) {
    if (event.keyCode === 13) {
      this.handleEnter();
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
};
```
