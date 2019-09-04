# サーバオブジェクト

サーバ情報を定義します。

## 固定フィールド

| フィールド名 | 型 | 説明 |
|---|---|:--|
| url | ``string`` | __【必須】__ 対象となるホストのURL。URLはサーバ変数をサポートします。また、ホストの配置先がOpenAPIが提供されるロケーションからの相対URLで示すために、相対URLをサポートします。変数名がブラケットに囲まれているとき（``{variable_name}``）に 変数と値の置き換えを行います。 |
| description | ``string`` | URLで示されるホストを説明する任意の文字列。リッチな表現のために[CommonMark](http://spec.commonmark.org/)シンタックスが使用【できます】。 |
| variables | Map\[``string``, [サーバ変数オブジェクト](ServerVariableObject.html)\] | 変数名と値を紐づけたマップ。値はサーバのURLテンプレートにおける変数の置換に使用します。 |



このオブジェクトは[仕様拡張](../SpecificationExtensions.html)にて追加定義を行うことが【可能】です。

## サーバオブジェクトサンプル

``` json
{
    "url": "http://development.gigantic-server.com/v1",
    "description": "Development Server"
}
```

``` yaml
url: http://development.gigantic-server.com/v1
description: Development Server
```

複数のサーバ情報を記載することができます。OpenAPIオブジェクトの[servers](OpenApiObject.html)フィールドがまさにそれです。

``` json
{
    "servers" : [
        {
            "url": "https://development.gigantic-server.com/v1",
            "description": "Development Server"
        },
        {
            "url": "https://staging.gigantic-server.com/v1",
            "description": "Staging Server"
        },
        {
            "url": "https://api.gigantic-server.com/v1",
            "description": "Production Server"
        }
    ]
}
```

``` yaml
servers:
- url: https://development.gigantic-server.com/v1
  descirpiton: Development Server
- url: https://staging.gigantic-server.com/v1
  descirpiton: Staging Server
- url: https://api.gigantic-server.com/v1
  descirpiton: Production Server
```

変数を使用する場合は以下のようになります。

``` json
{
  "servers": [
    {
      "url": "https://{username}.gigantic-server.com:{port}/{basePath}",
      "description": "The production API server",
      "variables": {
        "username": {
          "default": "demo",
          "description": "this value is assigned by the service provider, in this example `gigantic-server.com`"
        },
        "port": {
          "enum": [
            "8443",
            "443"
          ],
          "default": "8443"
        },
        "basePath": {
          "default": "v2"
        }
      }
    }
  ]
}
```

``` yaml
servers:
- url: https://{username}.gigantic-server.com:{port}/{basePath}
  description: The production API server
  variables:
    username:
      # 注意！ enumフィールドがないのは、固定の値だからです。
      default: demo
      description: this value is assigned by the service provider, in this example `gigantic-server.com`
    port:
      enum:
        - '8443'
        - '443'
      default: '8443'
    basePath:
      # 『固定』というのは、プロバイダから提供される特別な値がないということを意味します。
      # そのため、defaultフィールドの『v2』を使用します。
      default: v2
```
