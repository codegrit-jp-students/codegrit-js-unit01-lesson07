## for-in文

**_for-in文_**はオブジェクトの中身を取得して、その個数分だけ繰り返し処理ができます。
構文は次のようになります。

```js
for (変数 in オブジェクト) {
  文;
  文;
  文;
}
```

**_for-in文_**はオブジェクトに含まれるプロパティの個数分だけ繰り返し処理が行われ、そのつど変数の中にはオブジェクトのプロパティが代入されます。全ての繰り返し処理が終わると自動的にループが終了します。
オブジェクトを使った繰り返し処理で、既に学んだような通常の**_for文_**を使っても良いのですが、**_for-in文_**はfor文に比べてカウンタ変数を書く必要がなく記述が簡潔になります。繰り返し処理の中でカウンタ変数を使う必要のない場合などは**_for-in文_**を積極的に使うと良いでしょう。


変数はたとえば`let key`のように明示することもできますが、仮に`key`のように変数名のみを宣言したとしても、暗黙的に`let`で変数宣言されます。

- サンプルコード

次のサンプルコードの結果からもわかるように、変数にはオブジェクトの各値ではなく**プロパティ**が格納されることに注意してください。

```js
let obj = {
  a: 1,
  b: 2,
  c: 3
};

for (let item in obj) {
  console.log( item );
}
```

出力結果:

```
a
b
c
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/Lm5s694f/1/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>

オブジェクトの中身の値を取り出したい場合は、`obj[item]`のようにプロパティ名を指定して取り出すことができます。

```js
let obj = {
  a: 1,
  b: 2,
  c: 3
};

for (let item in obj) {
  console.log(obj[item]);
}
```

出力結果:

```javascript
1
2
3
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/zqn1egt9/2/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>

## for-of文

**_for-of文_**はES6から追加されました。**_for in文_**がオブジェクトの繰り返し処理に特化していた一方で、**_for-of文_**では**配列**に含まれる要素を変数として取り出し、配列の要素の数だけ繰り返し処理を行うことができるようになります。**_for in文_**と同様、**_カウンタ変数_**をわざわざ定義しなくてもいいのが特徴です。

構文は次のようになります。

```js
for (変数 of 配列) {
  文;
  文;
  文;
}
```

**_for in文_**の時と同じように、変数は変数名のみを宣言したとしても、暗黙的に`let`が付与されて変数宣言されます。

- サンプルコード

以下の例では、繰り返し処理の度に`item`に代入された配列要素を2倍にする処理を行なっています。

```javascript
let array = [10, 20, 30];

for (let item of array) {
  item = item * 2;
  console.log(item);
}
```

出力結果:

```javascript
20
40
60
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/aLs8uy6f/1/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>