# URL内での相対参照

他の方法では明示することなしに、URLの全プロパティは[RFC3986](https://tools.ietf.org/html/rfc3986#section-4.2)に定義されている相対参照です[^訳注1]。相対参照はベースURIとして[サーバーオブジェクト](Schema/ServerObject.html)で定義されているURLを使用して名前解決をします。

``$ref``で使用される相対参照はベースURIとして現在のドキュメントのURIを使用して、[JSONレファレンス](https://tools.ietf.org/html/draft-pbryan-zyp-json-ref-03)により処理されます。[参照オブジェクト](Schema/ReferenceObject.html)をあわせて参照してください。

[^訳注1]: 原文では ``MAY be relative references~`` となっている。
