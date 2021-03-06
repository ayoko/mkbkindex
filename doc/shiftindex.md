# How to use utils/shiftindex

shiftindex は、
mkbkindex ツールセットのための補助ツールです。
索引原稿を作ってから、台がズレるとがっかり＆うんざりしますが、このコマンドは、
今ある索引原稿の索引語に振られたノンブルを + or - にシフトします。
p.256-384は+2p、p.385以降は+4pなど、範囲を決めてシフトすることもできます。
mkbkindex で生成したファイルに対するパッチのような機能を果たします。

## 使い方の例

mkbkindex で出力した索引原稿 index_out.txt に対して、123ページから150ページで拾った索引語のノンブルだけ、
3ページ分、マイナスしたい場合を考えます。
125ページは 122ページに、140ページは 137ページに変更します。

その入力例を示します。

```
bash$ utils/shiftindex 123-150 -3 index_out.txt > index_new.txt
```

これによって、index_new.txt に修正済みの索引原稿が出力されます。

#ファイルの文字コードは、Shift JIS を前提としています。

## ページを後ろにずらす場合

上記例では -3 と書きましたが、これを +4 のように書けば、
後ろにずらすことができます。

## 実行方法

次のpythonコードを実行してください。

https://github.com/ayoko/mkbkindex/blob/master/utils/shiftindex

Python 2.1以上推奨
