## 分岐文

上から読んでも下から読んでもぶんきぶん...じゃないね。

という冗談はさておき分岐文です。

これまで難しいことやってたのでちょっと息抜き程度に簡単なのを持ってきました。



例
```
$a="ハンバーグ";
if(a=="ハンバーグ"){
  $this->getLogger()->notice("ハンバーグ大好き");
}else if(a=="フライドポテト"){
  $this->getLogger()->notice("フライドポテトも好き");
}else if(a=="やまいも"){
  $this->getLogger()->notice("やまいも...しぶいっすね。");
}else{
  $this->getLogger()->notice("そんな食べ物知らん。");
}
```

というネタプログラムがあって、これをきれいに短く書くのに分岐文を使います。


```
$a="ハンバーグ";
switch(a){
  case "ハンバーグ":
    $this->getLogger()->notice("ハンバーグ大好き");
    break;
  case "フライドポテト":
    $this->getLogger()->notice("フライドポテトも好き");
    break;
  case "やまいも":
    $this->getLogger()->notice("やまいも...しぶいっすね。");
    break;
  default:
    $this->getLogger()->notice("そんな食べ物知らん。");
    break;
}
```




公式です。

```
switch(確かめたい値){
  case 値1:
    // 実行したい文;
    break;
  case 値２:
    // 実行したい文;
    break;
  default:
    // 実行したい文;
    break;
}
```

なに？逆に長くなってるって？

switch文の特徴として見やすくなるというものがあります。

まあ、ほとんどはif文で足りると思います。



息抜きですから。