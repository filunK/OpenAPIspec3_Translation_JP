# 問い合わせオブジェクト

公開されたAPIの問い合わせ先情報です。

## 固定フィールド

| フィールド名 | 型 | 説明 |
|---|---|:--|
| name | ``string`` | 問い合わせ先の個人/組織の名前。 |
| url | ``string`` | 問い合わせ先情報のあるURL。URLのフォーマット【でなければならない】。 |
| email | ``string`` | 問い合わせ先の個人/組織へのメールアドレス。Eメールアドレスのフォーマット【でなければならない】。 |

このオブジェクトは[仕様拡張](../SpecificationExtensions.html)にて追加定義を行うことが【可能】です。

## 問い合わせオブジェクトサンプル

``` json
{
    "name": "API Support",
    "url": "https://www.example.com/support",
    "email": "support@email.com"
}
```

``` yaml
name: API Support
url: https://www.example.com/support
email: support@email.com
```
