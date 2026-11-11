# 階段を作ろう！

```blocks

let 開始位置: Position = null
function 階段を作る (開始位置: Position) {
    blocks.fill(
    GLASS,
    positions.add(
    開始位置,
    pos(-2, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(2, 3, 0)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(-1, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(1, 2, 0)
    ),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(0, 0, 5)
    )
    while (blocks.testForBlock(WATER, 開始位置)) {
        階段を作る(開始位置)
        開始位置 = positions.add(
        開始位置,
        pos(0, 1, 1)
        )
    }
})


```

```template

let 開始位置: Position = null
function トンネルを作る (開始位置: Position) {
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(0, 0, 5)
    )
})

```


## 地上へ続く階段をならべよう！ @unplugged
関数を使って、地上へつづく階段を作ろう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete3.gif">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・**ガラス**でできた階段を作ろう！
①変数``||variables.開始位置||``には、ブロックを並べ始める場所の座標が入っている
②関数``||functions.階段を作る||``の中に、下のような形にガラスを並べるようにプログラミングする
②階段の長さはわからないので、``||functions.階段を作る||``を``||variables.開始位置||``の場所に**水がなくなるまでくりかえし**呼び出して、地上までの階段にする
さっきまでとは、**階段を作る方向がちがう**ので注意しよう！
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_front_view3.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
今回は、トンネルを作る長さが分からないので、``||variables.開始位置||``が**水**の間はトンネルを作るようにします。
``||loops.もし～ならくりかえし||``と、``||blocks.～が(~0, ~0, ~0)に存在する||``、``||variables.開始位置||``を組み合わせましょう！
階段の形になるよう、``||variables.開始位置||``を**南と上に動かす**ことをわすれないようにしましょう！
<br></br>
むずかしいときは、**Theme3 Lesson8**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete3.gif">
<br></br>
できあがったのを確認したら、**村人に話しかけよう**

```blocks

let 開始位置: Position = null
function 階段を作る (開始位置: Position) {
    blocks.fill(
    GLASS,
    positions.add(
    開始位置,
    pos(-2, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(2, 3, 0)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(-1, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(1, 2, 0)
    ),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(0, 0, 5)
    )
    while (blocks.testForBlock(WATER, 開始位置)) {
        階段を作る(開始位置)
        開始位置 = positions.add(
        開始位置,
        pos(0, 1, 1)
        )
    }
})

```
