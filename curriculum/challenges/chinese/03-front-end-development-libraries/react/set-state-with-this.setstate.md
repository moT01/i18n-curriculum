---
id: 5a24c314108439a4d4036173
title: 用 this.setState 设置状态
challengeType: 6
forumTopicId: 301412
dashedName: set-state-with-this-setstate
---

# --description--

The previous challenges covered component `state` and how to initialize state in the `constructor`. There is also a way to change the component's `state`. React provides a method for updating component `state` called `setState`. You call the `setState` method within your component class like so: `this.setState()`, passing in an object with key-value pairs. The keys are your state properties and the values are the updated state data. For instance, if we were storing a `username` in state and wanted to update it, it would look like this:

```jsx
this.setState({
  username: 'Lewis'
});
```

React 要求永远不要直接修改 `state`，而是在 state 发生改变时始终使用 `this.setState()`。 此外，应该注意，React 可以批量处理多个 state 更新以提高性能。 这意味着通过 `setState` 方法进行的 state 更新可以是异步的。 `setState` 方法有一种替代语法可以解决异步问题， 虽然这很少用到，但是最好还是记住它！ 请查阅我们的 <a href="https://www.freecodecamp.org/chinese/news/what-is-state-in-react-explained-with-examples/" target="_blank" rel="noopener noreferrer nofollow">React 文章</a>了解更多详情。

# --instructions--

代码编辑器中有一个 `button` 元素，它有一个 `onClick()` handler。 当 `button` 在浏览器中接收到单击事件时触发此 handler，并运行 `MyComponent` 中定义的 `handleClick` 方法。 在 `handleClick` 方法中，使用 `this.setState()` 更新组件的 `state`。 设置 `state` 中的 `name` 属性为字符串 `React Rocks!`。

单击按钮查看渲染的 state 的更新。 如果不完全理解单击处理程序代码在此时的工作方式，请不要担心。 在接下来的挑战中会有讲述。

# --hints--

`MyComponent` 的 state 应该使用键值对 `{ name: Initial State }` 来初始化。

```js
assert(
  Enzyme.mount(React.createElement(MyComponent)).state('name') ===
    'Initial State'
);
```

`MyComponent` 应该渲染一个 `h1` 标题元素。

```js
assert(Enzyme.mount(React.createElement(MyComponent)).find('h1').length === 1);
```

渲染的 `h1` 标题元素应包含从组件状态渲染的文本。

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
  assert(/<h1>TestName<\/h1>/.test(firstValue));
};
```

调用 `MyComponent` 的 `handleClick` 方法应该将 state 的 name 属性设置为 `React Rocks!`。

```js
async () => {
  const waitForIt = (fn) =>
    new Promise((resolve, reject) => setTimeout(() => resolve(fn()), 250));
  const mockedComponent = Enzyme.mount(React.createElement(MyComponent));
  const first = () => {
    mockedComponent.setState({ name: 'Before' });
    return waitForIt(() => mockedComponent.state('name'));
  };
  const second = () => {
    mockedComponent.instance().handleClick();
    return waitForIt(() => mockedComponent.state('name'));
  };
  const firstValue = await first();
  const secondValue = await second();
  assert(firstValue === 'Before' && secondValue === 'React Rocks!');
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
      name: 'Initial State'
    };
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    // Change code below this line

    // Change code above this line
  }
  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me</button>
        <h1>{this.state.name}</h1>
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
      name: 'Initial State'
    };
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
     // Change code below this line
    this.setState({
      name: 'React Rocks!'
    });
    // Change code above this line
  }
  render() {
    return (
      <div>
        <button onClick = {this.handleClick}>Click Me</button>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```
