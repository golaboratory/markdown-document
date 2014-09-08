# CSSコーディングガイド

本ドキュメントは、CSSの記述におけるガイドラインを示したものである。

本ドキュメントの記述は全てのパターンを網羅したものではないため、記述外のガイドラインについては、プロジェクトの合意をもって運用されるものとする。


<br>
## CSSシンタックス

* セレクタをグループ化するとき、1行毎に1つのセレクタを記述すること
* 可読性のために、開き波括弧の前に1つの半角スペースをいれること
* 閉じ波括弧は新しい行に記述すること
* 各宣言は1行毎に記述すること（エラーがより的確に表示されるようになる）
* 全ての宣言の末尾にはセミコロンを付与すること
* hex型の値は全て小文字で記述すること（例: **#fff** ）

```css
/* 悪い例 */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* 良い例 */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}

```
<br>
## 宣言の順序

関連するプロパティは下記の順序でグルーピングすること

1. Positioning (位置関連)
1. Box Model (ボックスモデル)
1. Typographic (フォント関連)
1. Visual (見た目)

位置関係は場合によってボックスモデルを上書きする場合があるため、最初に記述する。

ボックスモデルは要素の大きさや位置を決定するため、その次に記述する。

その他の全ては、要素内の装飾となり、位置やボックス要素に関係しないので、最後に記述する。


```css

.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}

```
<br>

## クラス名

* クラス名は全て小文字で、ハイフンで結合を行うこと
* 過度な省略は行わないこと
* クラス名は意味のある名前にすること。見た目ではなく、機能や目的を意味する命名を行う
* 最も近い親要素やベースの要素をベースにプリフィックスすること
* スタイルではなく、挙動を制御するためのクラスには、 **js-***をプレフィックスとして使用すること（このクラスにはスタイルを定義してはならない）

```css

/* 悪い例 */
.t { ... }
.red { ... }
.header { ... }

/* 良い例 */
.tweet { ... }
.important { ... }
.tweet-header { ... }

```
