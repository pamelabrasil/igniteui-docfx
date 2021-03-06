﻿---
title: Switch コンポーネント
_description: Ignite UI for Angular Switch コンポーネントはアプリケーションにバイナリ有効/無効または true/false のデータ入力関数を追加します。
_keywords: Ignite UI for Angular, UI コントロール, Angular ウィジェット, web ウィジェット, UI ウィジェット, Angular, ネイティブ Angular コンポーネント スィート, ネイティブ Angular コントロール, ネイティブ Angular コンポーネント ライブラリ, Angular Switch コンポーネント, Angular Switch コントロール
_language: ja
---

## Switch

<p class="highlight">Ignite UI for Angular Switch コンポーネントは iOS の switch コンポーネントと同様に動作するバイナリ選択コンポーネントです。</p>
<div class="divider"></div>

### Switch デモ

<div class="sample-container loading" style="height:200px">
    <iframe id="form-elements-sample-iframe" src='{environment:demosBaseUrl}/switch-sample-2' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="form-elements-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で表示</button>
</div>
<div class="divider--half"></div>

### 使用方法

中核となるスイッチ コンポーネントはオン/オフ状態の切り替えが可能です。デフォルト スタイル設定はマテリアル デザイン ガイドラインの選択コントロールの仕様に基づきます。

Ignite UI for Angular Switch を初期化する前に、**IgxSwitchModule** を **app.module.ts** ファイルにインポートします。

```typescript
// app.module.ts

...
import { IgxSwitchModule } from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxSwitchModule],
    ...
})
export class AppModule {}
```

シンプルなスイッチを作成するには、コンポーネントのテンプレートで以下のコードを追加します。

```html
<igx-switch checked="true">
    Simple switch
</igx-switch>
```

以下は結果です。

<div class="sample-container" style="height: 150px">
<iframe src='{environment:demosBaseUrl}/switch-sample-1' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>

#### Switch プロパティ

上記のコードを拡張するには、スイッチ プロパティをデータにバインドします。name および state の 2 つのプロパティを持つ設定オブジェクトの配列があるとしましょう。スイッチ コンポーネントの checked プロパティを基本の設定オブジェクトの state プロパティにバインドします。同じように、value プロパティを name にバインドします。

```typescript
// toggle.component.ts
...
  public settings = [
    { name: 'WiFi', state: false},
    { name: 'Bluetooth', state: true},
    { name: 'Device visibility', state: false}
  ];

```

コンポーネント テンプレートに各設定のためのスイッチを追加し、相対するプロパティにバインドします。

```html
<!--toggle.component.html-->

<igx-switch *ngFor="let setting of settings" [checked]="setting.state">
  <div style="width: 150px">
      {{ setting.name }}
  </div>
</igx-switch>
```

結果は以下のようになります。

<div class="sample-container" style="height: 200px">
<iframe src='{environment:demosBaseUrl}/switch-sample-2' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>

### API まとめ

#### 入力

以下の入力が **igx-switch** コンポーネントで利用できます。

| 名前 | 型 | 説明 |
| :--- | :--- | :--- |
| `checked` | bool | true の場合、Switch が有効にされます。 |

<div class="divider"></div>

#### 出力

以下の出力が **igx-switch** コンポーネントで利用できます。

| 名前 | 型 | 説明 |
| :--- | :--- | :--- |
| `change` | EventEmitter | Switch をオンまたはオフにすると、イベントを発生します。 |

### 追加のリソース

<div class="divider--half"></div>
是非コミュニティに参加してください。

* [Ignite UI for Angular **フォーラム** (英語)](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub** (英語)](https://github.com/IgniteUI/igniteui-angular)
