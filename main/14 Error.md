## エラーメッセージ

実行したらなんか赤いやつ出た！
エラーの意味が分からん。

そんなものはなくしましょう

`[Server thread/CRITICAL]: ParseError: "syntax error, unexpected '}'" (EXCEPTION) in "plugins/Test_v1.0.0/src/tomo/Main" at line 18`

？？

`[サーバースレッド/致命的]: 解析エラー: "文法 エラー, 予期されない '}'" (例外) in "plugins/Test_v1.0.0/src/tomo/Main" at 18行目で`

`解析エラー: "plugins/Test_v1.0.0/src/tomo/Main"の18行目で文法 エラー 予期されない '}'が見つかりました。`

```
    public function onEnable()
    {
        $this->getServer()->getPluginManager()->registerEvents($this,$this);
        $this->getLogger()->notice("Eventを登録しました")
    }
```

行数を振らなくてもなにがダメかわかると思います。

セミコロンが抜けてますね。

実は`}`は18行目なのですが、問題は17行目にある。

エラーメッセージの行ばかりを見るのではなく、周辺も見るようにしましょう。