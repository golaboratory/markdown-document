# HTMLコーディングガイド

本ドキュメントは、HTMLの記述におけるガイドラインを示したものである。

本ドキュメントの記述は全てのパターンを網羅したものではないため、記述外のガイドラインについては、プロジェクトの合意をもって運用されるものとする。


<br>
## HTMLシンタックス

* ネストされた要素は必ず1段階だけインデントすること
* 常にダブルクォートを使用すること。要素に対してシングルクォートを使用してはならない
* 省略可能な閉じタグを省略しないこと　（例： **&lt;/li&gt;** や **&lt;/body&gt;** など）
* 要素は全て小文字で記述すること

```html

<!DOCTYPE html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>

```
<br>
## 要素の順序
HTMLの要素は可読性の向上のために、適切な順序で記述すること

1. class
1. id, name
1. data-*
1. src, for, type, href
1. title, alt

classは最も再利用されるコンポーネントなので最初に記述する

id,nameはより詳細に最小限のの使われ方をされるため、次に記述する

その他、エレメントによって固有のコンポーネントは最後に記述を行う

```html

<a class="..." id="..." data-modal="toggle" href="#">
  Example link
</a>

<input class="form-control" type="text">

<img src="..." alt="...">

```
<br>
## Javascriptによるマークアップ
Javascriptのファイルの中にマークアップを記述するのは、可読性を低下させ、検索しづらく、編集を難しくする上に、パフォーマンスが劣化する。可能な限り回避すること
