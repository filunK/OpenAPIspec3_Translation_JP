# フォーマット

OASに準拠するOpenAPIドキュメントはJSONオブジェクトで、JSONまたはYAMLのいずれかのフォーマットで表すことができます。

例えば、1つのフィールドでそれが配列の値である場合、JSONでは以下のようになります：

```JSON
{
    "field": [1, 2, 3]
}
```

仕様におけるすべてのフィールドでは大文字・小文字を区別します。これは、明確に『大文字・小文字の区別をしない』と注をしている箇所を除き、マップのキーとして使用する項目も含みます。

スキーマは2種類のフィールドからなります。宣言された名前を持つ固定フィールド、そしてフィールド名として正規表現で宣言されたパターンフィールドです。

パターンフィールドは含まれるオブジェクトの中でユニークな名前で【なければなりません】。

YAMLとJSONの相互変換ができるようにするため、YAMLバージョン[1.2](http://www.yaml.org/spec/1.2/spec.html)にいくつかの制約を加えた形が【推奨】されています。

* タグは[JSONスキーマルールセット](http://www.yaml.org/spec/1.2/spec.html#id2803231)で許可されているもの【でなければならない】。
* YAMLのマップで使用するキーは[YAMLフェイルセーフスキーマルールセット](http://yaml.org/spec/1.2/spec.html#id2802346)で定義されているスカラ文字列【でなければならない】。

__注：__ APIはYAMLまたはJSONフォーマットのOpenAPIドキュメントで定義しますが、APIリクエストとレスポンスボディ・他のコンテンツはJSONまたはYAMLである必要はありません。


