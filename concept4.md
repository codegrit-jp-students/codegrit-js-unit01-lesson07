## breakとcontinue

### break

**_break_**を使用することで繰り返しの途中でループを抜けることができます。**_break_**を実行するかどうかの判断は**_if文_**を使って制御することができます。
for文を例に**_break_**の処理の流れを見てみましょう。

```js
for (let i = 0; i < 10; i++) {
  処理1;
  if (条件式) break; // trueならばループを抜ける
  処理2;
}
```

この**_for文_**では処理1と処理2の間に**_if文_**を使った記述、`if(条件式) break;`が追加されています。もしこの**_if文_**の条件式が真であれば繰り返し処理の途中であってもループを抜けることになります。つまり処理2はスキップされます。

### continue

**_break_**では**_break_**が実行された瞬間にループを抜けました。
一方で**_continue_**は特定の回のループの中で以降の処理をスキップしたいときに使えます。
**_continue_**を実行するかは、**_break_**と同じように**_if文_**を使って決定することができます。
こちらも**_for文_**を例に処理の流れを見てみましょう。

```js
for (let i = 0; i < 10; i++) {
  処理1;
  if (条件式) continue; // trueならば処理2をスキップ
  処理2;
}
```

この**_for文_**では処理1と処理2の間に`if (条件式) continue;`が追加されています。この**_if文_**の条件式が真となり**_continue_**が実行された場合、すぐにカウンタ変数の変化式、つまり**_for文_**の`i++`が実行されます。従ってそれに続く処理2は実行されないまま次回のループ(厳密に言うと**_for文_**の条件式の評価)に移ることになります。

- サンプルコード

```js
for (let i = 0; i < 10; i++) {
  console.log(i);
  if (i % 5 === 0) {
    if (i === 0) {
      continue;
    } else {
      console.log('5の倍数なのでbreakします。');
      break;
    }
  }
}
```

出力結果：

```
0
1
2
3
4
5
5の倍数なのでbreakします。
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/nu3ajsx6/1/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>

## 更に学ぼう

### 動画で学ぶ

- [JavaScript入門 - ドットインストール](https://dotinstall.com/lessons/basic_javascript_v2)

### 本で学ぶ

- [Eloquent JavaScript 3rd Edition](http://eloquentjavascript.net/)
