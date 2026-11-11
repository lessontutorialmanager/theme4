# 小麦の俵をならべよう！

```blocks

player.onChat("run", function () {
    for (let index = 0; index < 3; index++) {
        blocks.fill(
        HAY_BLOCK,
        範囲の始まり,
        範囲の終わり,
        FillOperation.Replace
        )
        範囲の始まり = positions.add(
        範囲の始まり,
        pos(1, 1, 1)
        )
        範囲の終わり = positions.add(
        範囲の終わり,
        pos(-1, 1, -1)
        )
    }
})
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
範囲の始まり = world(137, 63, -341)
範囲の終わり = world(145, 63, -337)

```

```template

let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
範囲の始まり = world(137, 63, -341)
範囲の終わり = world(145, 63, -337)
player.onChat("run", function () {

})


```


## 小麦の俵をならべよう！ @unplugged
変数に座標を入れて、小麦の俵を3だん重ねよう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete3.png">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・``||positions.ワールド(137, 63, -341)||``から``||positions.ワールド(145, 63, -337)||``の範囲に**小麦の俵**を並べる
・小麦の俵は**3ブロック**の高さだけつみあげる
・ピラミッドのように、上の段ほどたてと横の大きさが小さくなるようにする
お手本を見て、どんな形かよく確認しよう！
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete3.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
変数``||variables.範囲の始まり||``と``||variables.範囲の終わり||``があります。
小麦の俵を並べる⇒``||variables.範囲の始まり||``と``||variables.範囲の終わり||``に入った座標を変える、を**3回**くりかえせばよさそうです！
<br></br>
むずかしいときは、**Theme2 Lesson4**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete3.png">
<br></br>
できあがったのを確認したら、**村人に話しかけよう**

```blocks

player.onChat("run", function () {
    for (let index = 0; index < 3; index++) {
        blocks.fill(
        HAY_BLOCK,
        範囲の始まり,
        範囲の終わり,
        FillOperation.Replace
        )
        範囲の始まり = positions.add(
        範囲の始まり,
        pos(1, 1, 1)
        )
        範囲の終わり = positions.add(
        範囲の終わり,
        pos(-1, 1, -1)
        )
    }
})
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
範囲の始まり = world(137, 63, -341)
範囲の終わり = world(145, 63, -337)

```
