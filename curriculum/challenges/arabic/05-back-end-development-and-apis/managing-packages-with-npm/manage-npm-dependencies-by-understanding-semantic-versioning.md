---
id: 587d7fb5367417b2b2512c01
title: إدارة اعتمادات npm بفهم بالإصدار الدلالي لنُسخ البرمجيات (Semantic Versioning)
challengeType: 2
forumTopicId: 301529
dashedName: manage-npm-dependencies-by-understanding-semantic-versioning
---

# --description--

`Versions` of the npm packages in the dependencies section of your package.json file follow what’s called Semantic Versioning (SemVer), an industry standard for software versioning aiming to make it easier to manage dependencies. Libraries, frameworks or other tools published on npm should use SemVer in order to clearly communicate what kind of changes projects can expect if they update.

معرفة SemVer مفيدة عند تطوير البرامج التي تستخدم التبعية الخارجية (التي تكاد تقوم بها دائما). يوما ما، فهمك لهذه الأرقام سوف يحفظك من إدخال تغييرات على مشروعك عن طريق الخطأ دون تفهم لماذا لا تعمل فجأة اليوم الأشياء التي عملت بالأمس. هذه هي الطريقة التي تعمل بها Semantic Versioning وفقا للموقع الرسمي على الإنترنت:

```json
"package": "MAJOR.MINOR.PATCH"
```

يجب أن يزداد رَقَم الإصدار MAJOR عند إجراء تغييرات API غير متوافقة. يجب أن يزداد رَقَم إصدار MINOR عند إضافة وظيفة بطريقة متوافقة رجعياً. يجب أن يزداد رَقَم الإصدار PATCH عند إجراء تصليحات للأخطاء متوافقة رجعيا. وهذا يعني أن PATCHES هي إصلاحات للأخطاء و MINORs تضيف ميزات جديدة ولكن كلا منهما لا يكسر ما كان يعمل من قبل. وأخيراً، يضيف MAJORs تغييرات لن تعمل مع الإصدارات السابقة.

# --instructions--

في قسم التبعيات من ملف الحزمة `package.json`، غيّر إصدار `@freecodecamp/example` لمطابقة قيمة إصدار 1 بنوع MAJOR وإصدار 2 بنوع MINOR وإصدار 13 بنوع PATCH

# --hints--

يجب أن تتضمن `"dependencies"` مقطع `"@freecodecamp/example"`.

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.property(
        packJson.dependencies,
        '@freecodecamp/example',
        '"dependencies" does not include "@freecodecamp/example"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

يجب أن يكون إصدار `"@freecodecamp/example"` بقيمة `"1.2.13"`.

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.equal(
        packJson.dependencies["@freecodecamp/example"],
        '1.2.13',
        'Wrong version of "@freecodecamp/example". It should be 1.2.13'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

