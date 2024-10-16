---
id: 587d7fb2367417b2b2512bf8
title: الحصول على البيانات من طلبات POST
challengeType: 2
forumTopicId: 301511
dashedName: get-data-from-post-requests
---

# --description--

Mount a POST handler at the path `/name`. It’s the same path as before. We have prepared a form in the html frontpage. It will submit the same data of exercise 10 (Query string). If the body-parser is configured correctly, you should find the parameters in the object `req.body`. Have a look at the usual library example:

<blockquote>route: POST '/library'<br>urlencoded_body: userId=546&#x26;bookId=6754 <br>req.body: {userId: '546', bookId: '6754'}</blockquote>

إستخدم نفس كائن JSON كما كان من قبل في الرد: `{name: 'firstname lastname'}`. اختبر ما إذا كانت نقطة النهاية (endpoint) تعمل باستخدام نموذج html الذي قدمناه في الصفحة الأمامية للتطبيق.

نصيحة: هناك العديد من طرق http الأخرى بخلاف GET و POST. ووفقًا للاتفاقية ، هناك تطابق بين فعل http والعملية التي ستقوم بتنفيذها على السيرفر. الخريطة التقليدية هي:

POST (في بعض الأحيان PUT) - إنشاء موّرد جديد باستخدام المعلومات المرسلة مع الطلب،

GET - قراءة مورد موجود دون تعديله،

PUT أو PATCH (أحيانا POST) - تحديث مورد باستخدام البيانات المرسلة،

DELETE - Delete a resource.

ويوجد أيضًا طريقتان أخريان تستخدمان للتفاوض مع الاتصال بالسيرفر. Except for GET, all the other methods listed above can have a payload (i.e. the data into the request body). يعمل البرنامج الوسيط (midleware) body-parser مع هذه الطرق أيضاً.

# --hints--

الاختبار 1: نقطة نهاية API الخاصة بك يجب أن تُرسل استجابة بالاسم الصحيح

```js
(getUserInput) =>
  $.post(getUserInput('url') + '/name', { first: 'Mick', last: 'Jagger' }).then(
    (data) => {
      assert.equal(
        data.name,
        'Mick Jagger',
        'Test 1: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

الاختبار 2: نقطة نهاية API الخاصة بك يجب أن ترسل استجابة بالاسم الصحيح

```js
(getUserInput) =>
  $.post(getUserInput('url') + '/name', {
    first: 'Keith',
    last: 'Richards'
  }).then(
    (data) => {
      assert.equal(
        data.name,
        'Keith Richards',
        'Test 2: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

