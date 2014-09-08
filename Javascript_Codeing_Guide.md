# Javascriptコーディングガイド

本ドキュメントは、Javascriptの記述におけるガイドラインを示したものである。

本ドキュメントの記述は全てのパターンを網羅したものではないため、記述外のガイドラインについては、プロジェクトの合意をもって運用されるものとする。

<br>
## Javascriptシンタックス

* 変数宣言には常に **var** をつけること
* 文字列値は常にシングルクォートを使用すること
* 行末は常にセミコロンを記述すること
* 処理系によって、暗黙のセミコロンが挿入されるのを防ぐため、開き波括弧は改行せずに記述すること
* 閉じ波括弧は新しい行に記述すること
* 可能な限り、関数の引数は一行で記述すること

```js
/* 変数宣言にはvarを使用する */
var rowIndex = 0;

/* 文字列値は常にシングルクォートを使用する */
var targetElemId = 'targetElem';

/* 開き括弧は改行せずに記述する */
if (rowIndex == 0) {
  // do something
}

/* 可能な限り引数は1行で記述する */
function sampleFunction(rowIndex, name, value, param1, param2, param3){
  // do something
}

/* 引数が長くなる場合は、このように複数行にわたってもよい */
function sampleFunctionTooLong(rowIndexForFoobarTable,
                               nameForFoobarTable,
                               valueForFoobarTextBox,
                               parameterForTestFunction){
  // do something
}

```

<br>
## 命名規則

命名のフォーマットは下記のように命名すること

* ファンクション名　functionNamesLikeThis
* 変数名　variableNamesLikeThis
* クラス名　ClassNamesLikeThis
* 列挙型名　EnumeNamesLikeThis
* 定数値　CONSTANTS_NAMES_LIKE_THIS
* Private な変数、メソッド _privateVarialblesLikeThis, _privateMethodsLikeThis

```js
/* ファンクション名 */
function sampleFunction(){
  //do something
}

var sampleFunction = function(){
  //do something
}

/* 変数名 */
var rowIndex = 0;
var sampleId = 'test';

/* クラス名 */
function Utility(){
  // this is constructor
}

/* 列挙型名 */
var LogLevel = {
  DEBUG: 0,
  INFO: 10,
  WARNING: 50,
  FATAL: 99
};

/* 定数値 */
var MAX_ROW_COUNT = 100;

/* privateな変数 */
var _rowIndex = 0;

/* privateなファンクション */
function _getRowIndex(){
  // do something
}

```

<br>
## 名前空間の使用
グローバルスコープに出すファンクション、及び変数については、プロジェクトやライブラリ名に関連した名前空間をプレフィックスとして使用すること

名前空間を使用することで、ファンクション名や変数名の衝突を避けることができる

```js

/* proj という名前空間を作成 */
var proj = {};

var proj.someFunction = function(){
  // do something
};

/* アクセス方法 */
proj.someFunction();

```

<br>
## コメント
VisualStudioを使用してJavascriptの記述を行う場合、下記のようにFunctionのXMLドキュメントコメントを記述すること

各要素は1行で記述を行うこと

この記述はVisualStudioのIntelliSenseによって使用されます

```js
function someFunction(numParam) {
    /// <summary>引数値を二乗した値を取得する</summary>
    /// <param name="numParam" Type="Number">二乗する値</param>
    /// <returns type="Number">引数の二乗値</returns>

    return numParam * numParam;

}
```
