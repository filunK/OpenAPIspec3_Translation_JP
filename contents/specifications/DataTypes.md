# データ型

OASにおけるプリミティブ型は[JSONスキーマ仕様ドラフト00](https://tools.ietf.org/html/draft-wright-json-schema-00#section-4.2)にてサポートされている型をもとにしています。注意すべきは``integer``型は小数部や指数部を持たないJSON numberとして定義・サポートされている点です。``null``型はサポートされていません（代替方法として[nullable](Schema/SchemaObject.html)を参照してください。）。

プリミティブ型は任意の修正プロパティ``format``を持ちます。OASはデータの詳細を定義するために数種類の知られたフォーマットを使用します。しかし、ドキュメンテーションのニーズをサポートするために、``format``プロパティは``string``型で何らかの値を持つことができます。``email``や``uuid``などといったフォーマットは仕様によっては未定義であっても使用される【かもしれません】。 ``format``プロパティを伴わない型はJSONスキーマに定義されている内容に従います。特定の``format``を認識しないツールは、フォーマットが指定されていない場合と同様、デフォルトの定義に回帰します。

| 型(type) | フォーマット(format) | コメント |
|---|---|:--|
| integer | int32 | 符号付32ビット |
| integer | int64 | 符号付64ビット(またはlong)  |
| number | float |   |
| number | double |   |
| string |   |   |
| string | byte | BASE64エンコード |
| string | binary | オクテットのシーケンス |
| boolean |   |   |
| string | date | [RFC3339](https://xml2rfc.ietf.org/public/rfc/html/rfc3339.html#anchor14)にて``full-date``として定義 |
| string | date-time | [RFC3339](https://xml2rfc.ietf.org/public/rfc/html/rfc3339.html#anchor14)にて``date-time``として定義 |
| string | password | 入力値を隠すためのUIに対するヒント |
