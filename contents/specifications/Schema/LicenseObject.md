# ライセンスオブジェクト

公開されたAPIのライセンス情報です。

## 固定フィールド

| フィールド名 | 型 | 説明 |
|---|---|:--|
| name | ``string`` | __【必須】__ APIに適用するライセンスの名前。 |
| url | ``string`` | ライセンス条項が記載されたURL。URLのフォーマット【でなければならない】。 |

このオブジェクトは[仕様拡張](../SpecificationExtensions.html)にて追加定義を行うことが【可能】です。

## ライセンスオブジェクトサンプル

``` json
{
    "name": "Apache 2.0",
    "url": "https://www.apache.org/lisence/LICENSE-2.0.html"
}
```

``` yaml
name: Apache 2.0
url: https://www.apache.org/lisence/LICENSE-2.0.html
```
