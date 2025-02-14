---
title: CustomEvent.detail
slug: Web/API/CustomEvent/detail
page-type: web-api-instance-property
tags:
  - プロパティ
  - リファレンス
  - 読み取り専用
browser-compat: api.CustomEvent.detail
translation_of: Web/API/CustomEvent/detail
---
{{APIRef("DOM")}}

**`detail`** は {{domxref("CustomEvent")}} インターフェイスの読み取り専用プロパティで、イベントを初期化する際に渡された何らかのデータを返します。

## 値

イベントの初期化に使用したデータです。

## 例

```js
// カスタムイベントを作成
const catFound = new CustomEvent('animalfound', {
  detail: {
    name: 'cat'
  }
});
const dogFound = new CustomEvent('animalfound', {
  detail: {
    name: 'dog'
  }
});

// 適切なイベントリスナーを追加
obj.addEventListener('animalfound', (e) => console.log(e.detail.name));

// イベントの配信
obj.dispatchEvent(catFound);
obj.dispatchEvent(dogFound);

// "cat" および "dog" がコンソールの出力される
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{domxref("CustomEvent")}}
