## 繰り返しの文

何度も繰り返したい...そんなことはありませんか？

例：１～１０まで表示したい

そこの、『ひとつひとつ`$this->getLogger()->notice("~~");`を書けばいいじゃん』と思ってるあなた。

つぎは１００まで...というと死にます。これを楽にやるのがfor文とwhile文の力です。

```
for(初期化式;条件式;操作){
  // 繰り返す文;
}
```

(´-ω-`)ワカラン。

例：
```
for($a=1;$a<=10;$a++){
    $this->getLogger()->notice("\$a=".$a);
}
```

(なんで`\$a`にしてるかは`$a`に変えてみるとわかります)

これは1~10まで出力するプログラムです。

流れとしては、



１．for発見！

２．はじめの数を見る

３．条件式を見る

４．trueなら実行(falseなら{}のそとへ)

５．{}が終わったら操作をする

６．３にもどる



という感じになる。



次にwhile文。for文と近いが勝手が違う

```
while(条件式){
    // 実行する文;
}
```


こっちのほうが簡単じゃんと思うかもしれないが、こっちは一歩間違えると無限ループする。

カッコの中がtrueのときに繰り返し実行する。

for文やwhile文を強制的に止めたいときにはbreakやcontinueを使う。

breakとcontinueの違いは、ループの外に出るか出ないかの違いです。

breakは呼び出されたときにループの外に出る。

continueは呼び出されたときに初めに戻る。

という違いがあります。


### foreach

```
foreach ($this->getServer()->getOnlinePlayers() as $p) {
    // 処理
}
```
と書きます。

`for`を使わない理由としては`for`はあくまで条件を満たしてる間をループさせるだけで、なんかの配列のitemを抽出してくれるわけではありません。

？？ってなったと思いますが、`$this->getServer()->getOnlinePlayers()`は現在オンライン(サーバー内にいる)のプレイヤーの一覧を返してくれます。

何番目かを知りたいわけではないのでループ時にプレイヤー、一人ひとりが変数に入れられる`foreach`のほうが便利ってことです。