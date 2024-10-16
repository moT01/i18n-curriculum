---
id: 5a24c314108439a4d403614f
title: أرسال حدث أجراء (Action Event)
challengeType: 6
forumTopicId: 301442
dashedName: dispatch-an-action-event
---

# --description--

`dispatch` method is what you use to dispatch actions to the Redux store. Calling `store.dispatch()` and passing the value returned from an action creator sends an action back to the store.

Recall that action creators return an object with a type property that specifies the type of action that has occurred. ثم ترسل الطريقة dispatches كائن إجراء (action) إلى متجر Redux. استنادا إلى مثال التحدي السابق، الأسطر التالية متساويا، وكلاهما يرسل إجراء من نوع `LOGIN`:

```js
store.dispatch(actionCreator());
store.dispatch({ type: 'LOGIN' });
```

# --instructions--

لدي متجر (store) من Redux في محرر الكود حالة (state) تهيئة تحتوي على كائن (object) يحتوي على خاصية (property) تسمى `login` بحالة `false` حالياً. هناك أيضا منشئ عمل يسمى `loginAction()` الذي ينتج إجراء من نوع `LOGIN`. إرسال إجراء `LOGIN` إلى متجر Redux عن طريق الاتصال بطريقة `dispatch`، و اجتاز الإجراء الذي أنشأه `loginAction()`.

# --hints--

الاتصال بالوظيفة `loginAction` يجب أن يعيد كائن يحمل مجموعة الخصائص `type` من string باسم `LOGIN`.

```js
assert(loginAction().type === 'LOGIN');
```

يجب تهيئة المتجر مع كائن ذو خاصية `login` بقيمة `false`.

```js
assert(store.getState().login === false);
```

يجب استخدام طريقة `store.dispatch()` لإرسال إجراء من نوع `LOGIN`.

```js
(getUserInput) =>
  assert(
    (function () {
      let noWhiteSpace = getUserInput('index').replace(/\s/g, '');
      return (
        noWhiteSpace.includes('store.dispatch(loginAction())') ||
        noWhiteSpace.includes("store.dispatch({type: 'LOGIN'})") === true
      );
    })()
  );
```

# --seed--

## --seed-contents--

```js
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

// Dispatch the action here:
```

# --solutions--

```js
const store = Redux.createStore(
  (state = {login: false}) => state
);

const loginAction = () => {
  return {
    type: 'LOGIN'
  }
};

store.dispatch(loginAction());
```
