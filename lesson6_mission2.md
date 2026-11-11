# 長さのわからないトンネルを作ろう！

```blocks

let 開始位置: Position = null
function トンネルを作る (開始位置: Position) {
    blocks.fill(
    GLASS,
    positions.add(
    開始位置,
    pos(0, 0, -2)
    ),
    positions.add(
    開始位置,
    pos(0, 3, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(0, 0, -1)
    ),
    positions.add(
    開始位置,
    pos(0, 2, 1)
    ),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(2, 0, 0)
    )
    while (blocks.testForBlock(WATER, 開始位置)) {
        トンネルを作る(開始位置)
        開始位置 = positions.add(
        開始位置,
        pos(1, 0, 0)
        )
    }
})





```

```template

let 開始位置: Position = null
function トンネルを作る (開始位置: Position) {
    blocks.fill(
    GLASS,
    positions.add(
    開始位置,
    pos(0, 0, -2)
    ),
    positions.add(
    開始位置,
    pos(0, 3, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(0, 0, -1)
    ),
    positions.add(
    開始位置,
    pos(0, 2, 1)
    ),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(2, 0, 0)
    )
    for (let index = 0; index < 7; index++) {
        トンネルを作る(開始位置)
        開始位置 = positions.add(
        開始位置,
        pos(1, 0, 0)
        )
    }
})

```


## 長さのわからないトンネルを作ろう！ @unplugged
関数を使って、むこうがわまでトンネルを作ろう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete2.gif">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・**ガラス**でできたトンネルを作ろう！
①変数``||variables.開始位置||``には、ブロックを並べ始める場所の座標が入っている
②関数``||functions.トンネルを作る||``の中に、下のような形にガラスを並べるようにプログラミングする
②トンネルの長さはわからないので、``||functions.トンネルを作る||``を``||variables.開始位置||``の場所に**水がなくなるまでくりかえし**呼び出して、向こう側までのトンネルにする
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_tunnel2.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
今回は、トンネルを作る長さが分からないので、``||variables.開始位置||``が**水**の間はトンネルを作るようにします。
``||loops.もし～ならくりかえし||``と、``||blocks.～が(~0, ~0, ~0)に存在する||``、``||variables.開始位置||``を組み合わせましょう！
<br></br>
むずかしいときは、**Theme3 Lesson5**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete2.gif">
<br></br>
できあがったのを確認したら、**管理人に話しかけよう**

```blocks

let 開始位置: Position = null
function トンネルを作る (開始位置: Position) {
    blocks.fill(
    GLASS,
    positions.add(
    開始位置,
    pos(0, 0, -2)
    ),
    positions.add(
    開始位置,
    pos(0, 3, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(0, 0, -1)
    ),
    positions.add(
    開始位置,
    pos(0, 2, 1)
    ),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    開始位置 = positions.add(
    player.position(),
    pos(2, 0, 0)
    )
    while (blocks.testForBlock(WATER, 開始位置)) {
        トンネルを作る(開始位置)
        開始位置 = positions.add(
        開始位置,
        pos(1, 0, 0)
        )
    }
})

```
