## 命令・変数・宣言

いきなり難しそうですね...。だけどまだまだ基礎of基礎です。

それではひとつずつ説明していきます。

↓前回のコード
```
<?php

declare(strict_types=1);

namespace tomo;

use pocketmine\plugin\PluginBase;

class Main extends PluginBase
{

    public function onEnable()
    {
        $this->getLogger()->notice("Test plugin was loaded!");
    }

    public function onDisable()
    {
        $this->getLogger()->notice("Test plugin was unloaded!");
    }
}
```

### 命令

さて、さっそくプログラムをかいてもらったわけですが、

意味が分からないと意味がないです。というか、書けません。

まず1行目`<?php`からわからないと思いますが、これは僕がphpだよ！！って言ってるだけです。

そして3行目`declare(strict_types=1);`はphpの機能で型を厳しくしてます。型については後ほど

そして12行目`public function onEnable()`はpmmpの組み込み関数のひとつで、

簡単に言うとプラグインが有効化されたら、{}の中を実行するという意味です。

そして14行目`$this->getLogger()->notice("Test plugin was loaded!");`ですが、これはpmmpに組み込んである命令というものです。

命令というのは、決まった書き方（公式みたいなもの）があり、それに従って書かなくてはいけません。

`$this->getLogger()->notice("出したい言葉");`で書きます。

これであの画像のようにコンソールにメッセージが出ます。

必ず、`"`で囲ってください。

命令というものは書くだけでその命令に対応したことを実行してくれます。

そしてそのあとの；(セミコロン)ですがこれはプログラムの行の終わりを示します。

(これがないとエラー吐く。)

プログラミング言語の中では改行をしても次の行の判定にならない言語があります

phpもその一種です。

なので、命令と命令の間には絶対に；を書きましょう。


### 変数・宣言

しばらくはminecraftやpmmpと関係ないのですが、頑張りましょう。

次に変数です。変数というのは「好きに変えられる数」です。(そのまま)

よくわからないと思いますから、onEnable()関数の中の処理をいじってみましょう。

```
public function onEnable()
    {
        $A = 0;
        $this->getLogger()->notice("数字は".$A."です");
    }

```

これを実行すると`[Server thread/NOTICE]: [Test] 数字は0です`と出力されます。

もうちょっと見てみましょう。

```
public function onEnable()
    {
        $A = 0;
        $A = $A + 1;
        $this->getLogger()->notice("数字は".$A."です");
    }
```

実行すると```[Server thread/NOTICE]: [Test] 数字は1です```と出力されます。

？？？

変数というのは簡単に言うとバケツみたいなものです

![bucket](http://minecraftpemodcreate.web.fc2.com/png/backetempty.png)

バケツを用意する作業を宣言といいます

宣言の仕方にはいくつかあります。

```
$アルファベット;

$アルファベット=数字;

$アルファベット="文字";

などなど...
```

バケツを用意してから入れてもいいし、バケツに入れたものを用意してもいい。

次に、`$A=$A+1;`ですが、バケツと思えば簡単ですね。

Aという名前のバケツにもともと入ってた液体＋１をAのバケツに入れる

ってかんじですかね。(わかりづらいかな？)

変数の中に数や文字を入れることを代入するといいます。

じゃあ練習問題で確かめよう

練習問題
```
$A=2;
$B=3;
$A=$B+$A+$A+4;
```
とやると$Aになにが入るでしょう。

　

考え方

`$A=3+2+2+4`で`11`が入る。

変数ははじめの難関ですが分かったでしょうか？

また、なんでも変数の名前を付けられるかというとそうではありません。

変数の名前の条件

* 予約語でない。(if,for,while.....など以外)

* 半角英数字である。

* 記号は_のみ使える。

* 大文字と小文字は別物

また変数にもルールがあります。

* 同じ名前の変数は同じ{}の中で１つ。もう一回作ると昔のやつは消える。

* 別の{}の中にある変数は別物だし、使うことができない。

まあ。慣れないと思いますが、使ってればだんだん慣れます。

余談：

　この世の中には、いっぱいプログラマがいます。その人が別々のルールでコードを書いていたら収拾がつきませんね。
　そこで、こういう決まりにしよう！というコーディング規約というものがあります。(もちろんプログラミング言語ごとにあります。)
　このページでは作者が自由気ままに書いているので、守っていないことがあります。ご了承を。