# OpenAPIオブジェクト

[OpenAPIドキュメント](../../definitions/Definitions.html)のルートオブジェクトです。

## 固定フィールド

| フィールド名 | 型 | 説明 |
|---|---|:--|
| openapi | ``string`` | __【必須】__文字列はOpenAPIドキュメントが使用する[OASバージョン](../../Versioon.html) の [semver](https://semver.org/spec/v2.0.0.html)で【なければ】なりません。``openapi``フィールドはツールにはバージョン指定を、クライアントにはOpenAPIドキュメントの解釈をするために使用される【べき】です。このフィールドはAPIの``info.version``文字列とは __関連がありません__ 。 |
| info | [情報オブジェクト](InfoObject.html) | __【必須】__ APIのメタデータを提供します。メタデータはツールには必須のものとして用いられます。  |
| servers | \[[サーバオブジェクト](ServerObject.html)\] | Serverオブジェクトの配列です。対象サーバに対する接続情報を提供します。``server``フィールドが定義されない、またはカラの配列である場合、urlフィールドに``/``が設定された[サーバオブジェクト](ServerObject.html)が設定されているものとみなします。 |
| paths | [パスオブジェクト](PathObject.html) | __【必須】__ APIとして利用可能なパスや操作。 |
| components | [コンポネントオブジェクト](ComponentsObject.html) | 仕様におけるさまざまなスキーマを保持する要素。 |
| security | \[[セキュリティ要求オブジェクト](SecurityRequirementObject.html)\]  | APIにおいてどのセキュリティ方式が使用されるかを宣言するもの。リストには代替可能なセキュリティ要求オブジェクトを含みます。リクエストを認証する為には1つのセキュリティ要求オブジェクトを満たす必要があります。それぞれの操作でこの定義を上書きすることができます。 |
| tags | \[[タグオブジェクト](TagObject.html)\] | 追加のメタデータを伴う仕様にて使用するタグのリスト。タグの順序はツールによるパースの際の順番に反映されます。[操作オブジェクト](OperationObject.html)で使用されるタグのすべてが宣言されなければいけないわけではありません。宣言されていないタグはランダムまたはツールの実装に任されます[^脚注1] 。 |
| externalDocs | [外部ドキュメントオブジェクト](ExternalDocumentationObject.html) | 追加の外部ドキュメント。 |

OpenAPIオブジェクトは[仕様拡張](../SpecificationExtensions.html)にて追加定義を行うことが【可能】です。


[^脚注1]: 原文では ``MAY be organized`` となっている。
