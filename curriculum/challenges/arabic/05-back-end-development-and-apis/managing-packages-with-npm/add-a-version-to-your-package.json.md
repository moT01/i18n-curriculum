---
id: 587d7fb4367417b2b2512bff
title: إضافة رقم الإصدار (Version) إلى package.json
challengeType: 2
forumTopicId: 301525
dashedName: add-a-version-to-your-package-json
---

# --description--

A `version` is one of the required fields of your package.json file. This field describes the current version of your project. إليك مثال:

```json
"version": "1.2.0",
```

# --instructions--

أضف `version` إلى ملف package.json لمشروعك.

# --hints--

يجب أن يحتوي package.json على هوية "version" صحيحة

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert(packJson.version, '"version" is missing');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

