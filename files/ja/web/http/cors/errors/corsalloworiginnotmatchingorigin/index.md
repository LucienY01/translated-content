---
title: 'Reason: CORS header ''Access-Control-Allow-Origin'' does not match ''xyz'''
slug: Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin
tags:
  - CORS
  - CORSAllowOriginNotMatchingOrigin
  - HTTP
  - HTTPS
  - エラー
  - オリジン間
  - コンソール
  - セキュリティ
  - トラブルシューティング
  - メッセージ
  - 理由
translation_of: Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin
---
{{HTTPSidebar}}

## 理由

```
Reason: CORS header 'Access-Control-Allow-Origin' does not match 'xyz'
```

## 何が悪いのか

リクエストを作成しているオリジンが、 {{HTTPHeader("Access-Control-Allow-Origin")}} ヘッダーによって許可されたオリジンのいずれにも一致しないことを表します。

このエラーは、レスポンスに複数の `Access-Control-Allow-Origin` ヘッダーが含まれていると発生することがあります。

コードが CORS リクエストを使用してアクセスしているサービスが管理下にあるのであれば、 `Access-Control-Allow-Origin` ヘッダーがそのアクセス元が含むように構成されていること、及びそのヘッダーがレスポンス内に 1 つしか含まれていないことを確認してください。ヘッダー自体はコンマ区切りで複数のオリジンを受け付けるので、新しいオリジンを追加することは難しくはありません。

例えば Apache では、サーバー構成 (の中の `<Directory>`, `<Location>`, `<Files>`, `<VirtualHost>` のうち適切な節) に次のような行を追加してください。構成はふつう、 `.conf` ファイル又は (一般的な名前は `httpd.conf` や `apache.conf`) 又は `.htaccess` ファイルにあります。

```
Header set Access-Control-Allow-Origin 'origin-list'
```

Nginx では、このヘッダーを設定するコマンドは次の通りです。

```
add_header 'Access-Control-Allow-Origin' 'origin-list'
```

## 関連情報

- [CORS のエラー](/ja/docs/Web/HTTP/CORS/Errors)
- 用語集: {{Glossary("CORS")}}
- [CORS 入門](/ja/docs/Web/HTTP/CORS)
- [Enable CORS: I want to add CORS support to my server](https://enable-cors.org/server.html)
