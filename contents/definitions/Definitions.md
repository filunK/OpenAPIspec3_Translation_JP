# 定義

本ドキュメントに登場する用語について説明します。

## OpenAPIドキュメント

APIを定義・説明するドキュメント（またはドキュメントの集まり）。OpenAPI定義はOASに準拠します。

## パステンプレーティング

URLの中の置き換え可能な箇所を波かっこ（{}）を囲うことで、パスパラメータによる置き換えができます。

## メディアタイプ

メディアタイプ定義はリソースの種類に応じて多岐にわたります。メディアタイプ定義は [RFC6838](https://tools.ietf.org/html/rfc6838) に従う【べき】です。

利用可能なメディアタイプ定義の例：

```
text/plain; charset=utf-8
application/json
application/vnd.github+json
application/vnd.github.v3+json
application/vnd.github.v3.raw+json
application/vnd.github.v3.text+json
application/vnd.github.v3.html+json
application/vnd.github.v3.full+json
application/vnd.github.v3.diff
application/vnd.github.v3.patch
```

## HTTPステータスコード

HTTPステータスコードは実行された操作の状態を示すために使われます。利用可能なステータスコードは[RFC7231](https://tools.ietf.org/html/rfc7231#section-6)に定義されており、登録されているステータスコードは[IANAステータスコードリポジトリ](https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)に一覧があります。


