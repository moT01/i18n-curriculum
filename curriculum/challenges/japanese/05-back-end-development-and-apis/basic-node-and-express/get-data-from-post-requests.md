---
id: 587d7fb2367417b2b2512bf8
title: POST リクエストからデータを取得する
challengeType: 2
forumTopicId: 301511
dashedName: get-data-from-post-requests
---

# --description--

Mount a POST handler at the path `/name`. It’s the same path as before. We have prepared a form in the html frontpage. It will submit the same data of exercise 10 (Query string). If the body-parser is configured correctly, you should find the parameters in the object `req.body`. Have a look at the usual library example:

<blockquote>route: POST '/library'<br>urlencoded_body: userId=546&#x26;bookId=6754 <br>req.body: {userId: '546', bookId: '6754'}</blockquote>

前回と同じ JSON オブジェクト `{name: 'firstname lastname'}` で応答してください。 アプリのフロントページに提供されている html フォームを使用してエンドポイントが動作するかどうかをテストしてください。

ヒント: GET と POST 以外にもいくつかの http メソッドがあります。 慣例として、http 動詞とサーバ上で実行する操作には対応関係があります。 従来の対応関係は以下のようになっています。

POST (場合によっては PUT) - リクエストと共に送信された情報を使用して新しいリソースを作成する。

GET - 既存のリソースを変更せずに読み取る。

PUT または PATCH (場合によっては POST) - 送信されたデータを使用してリソースを更新する。

DELETE - Delete a resource.

他にもサーバーとの接続のやり取りに使用するメソッドがいくつかあります。 Except for GET, all the other methods listed above can have a payload (i.e. the data into the request body). ボディ解析ミドルウェアでもこれらのメソッドを使用できます。

# --hints--

テスト 1: API エンドポイントは、正しい名前で応答する必要があります。

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

テスト 2: API エンドポイントは、正しい名前で応答する必要があります。

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

