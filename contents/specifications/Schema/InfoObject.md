# 情報オブジェクト

APIのメタデータを提供します。必要に応じてクライアントがメタデータを使用することが【でき】、編集またはドキュメント生成ツールの利便性のために提供する事が【でき】ます。

## 固定フィールド

| フィールド名 | 型 | 説明 |
|---|---|:--|
| title | ``string`` | __【必須】__ アプリケーションの名前。 |
| description | ``string`` | アプリケーションの短い説明。より良い表現のため[CommonMark](http://spec.commonmark.org/)シンタックスが使用【できます】。 |
| termsOfService | ``string`` | APIの利用規約のURL。URLのフォーマット【でなければならない】。 |
| contact | [問い合わせオブジェクト](ContactObject.html) | 公開されたAPIの問い合わせ先情報。 |
| license | [ライセンスオブジェクト](LicenseObject.html) | 公開されたAPIのライセンス情報。 |
| version | ``string`` | __【必須】__ OpenAPIドキュメントのバージョン（OASバージョンやAPI実装のバージョンとは異なります） |

このオブジェクトは[仕様拡張](../SpecificationExtensions.html)にて追加定義を行うことが【可能】です。

## 情報オブジェクトサンプル

``` json
{
    "title": "Sample Pet Store App",
    "description": "This is a sample server for a pet store.",
    "termOfService": "https://example.com/terms/",
    "contact": {
        "name": "API Support",
        "url": "https://www.example.com/support",
        "email": "support@email.com"
    },
    "license" : {
        "name": "Apache 2.0",
        "url": "https://www.apache.org/lisence/LICENSE-2.0.html"
    },
    "version": "1.0.1"
}
```

``` yaml
title: Sample Pet Store App
description: This is a sample server for a pet store.
termOfService: https://example.com/terms/
contact:
    name: API Support
    url: https://www.example.com/support
    email: support@email.com
license:
    name: Apache 2.0
    url: https://www.apache.org/lisence/LICENSE-2.0.html
version: 1.0.1
```
