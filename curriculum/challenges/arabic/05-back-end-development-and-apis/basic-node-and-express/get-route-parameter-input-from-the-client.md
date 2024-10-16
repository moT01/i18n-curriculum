---
id: 587d7fb2367417b2b2512bf5
title: الحصول على إدخال معلمة المسار من العميل
challengeType: 2
forumTopicId: 301513
dashedName: get-route-parameter-input-from-the-client
---

# --description--

When building an API, we have to allow users to communicate to us what they want to get from our service. For example, if the client is requesting information about a user stored in the database, they need a way to let us know which user they're interested in. One possible way to achieve this result is by using route parameters. Route parameters are named segments of the URL, delimited by slashes (/). Each segment captures the value of the part of the URL which matches its position. The captured values can be found in the `req.params` object.

<blockquote>route_path: '/user/:userId/book/:bookId'<br>actual_request_URL: '/user/546/book/6754' <br>req.params: {userId: '546', bookId: '6754'}</blockquote>

# --instructions--

قم ببناء خادم استجابة محمول في المسار `GET /:word/echo`. الرد بكائن JSON يأخذ التركيب `{echo: word}`. يمكنك العثور على الكلمة المراد تكرارها في `req.params.word`. يمكنك اختبار مسارك من شريط عنوان المتصفح الخاص بك ، وزيارة بعض المسارات المطابقة ، على سبيل المثال `your-app-rootpath/freecodecamp/echo`.

# --hints--

الاختبار 1 : خادم الاستجابة الخاص بك يجب أن يكرر الكلمات بشكل صحيح

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/eChOtEsT/echo').then(
    (data) => {
      assert.equal(
        data.echo,
        'eChOtEsT',
        'Test 1: the echo server is not working as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

الاختبار 2 : خادم الاستجابة الخاص بك يجب أن يكرر الكلمات بشكل صحيح

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/ech0-t3st/echo').then(
    (data) => {
      assert.equal(
        data.echo,
        'ech0-t3st',
        'Test 2: the echo server is not working as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

