# 畑をつくろう！

```blocks

let 開始位置: Position = null
let 作物 = 0
player.onChat("set", function () {
    開始位置 = player.position()
    作物 = CROPS
})
player.onChat("run", function () {
    for (let index = 0; index < 2; index++) {
        blocks.fill(
        FARMLAND,
        positions.add(
        開始位置,
        pos(1, -1, 1)
        ),
        positions.add(
        開始位置,
        pos(9, -1, 9)
        ),
        FillOperation.Replace
        )
        blocks.place(WATER, positions.add(
        開始位置,
        pos(5, -1, 5)
        ))
        blocks.fill(
        作物,
        positions.add(
        開始位置,
        pos(1, 0, 1)
        ),
        positions.add(
        開始位置,
        pos(9, 0, 9)
        ),
        FillOperation.Replace
        )
        開始位置 = positions.add(
        開始位置,
        pos(9, 0, 1)
        )
        作物 = CARROTS
    }
})




```

```template

let 開始位置: Position = null
let 作物 = 0
player.onChat("set", function () {
    開始位置 = player.position()
    作物 = CROPS
})

```


## 畑をつくろう！ @unplugged
変数を使って、小麦とニンジンの畑をつくろう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete2.png">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・**東に9ブロック**、**南に9ブロック**の畑を**2つ**つくる
・畑がかわかないように、畑の真ん中に**水**をおく
①**白色の彩釉テラコッタ**に近いほうの畑(下の画像の**左側**)には、**小麦**を植える
②もうひとつの畑(下の画像の**右側**)には、**ニンジン**を植える
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_top_view2.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
変数``||variables.開始位置||``と``||variables.作物||``があります。
下の図のように、**小麦の畑を並べる**⇒``||variables.開始位置||``に入った座標と``||variables.作物||``に入った作物の種類を変える⇒**ニンジンの畑を並べる**、という順になるようにプログラミングしてみましょう！
<br></br>
むずかしいときは、**Theme2 Lesson6**を復習してみよう！
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_move3.gif">



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete2.png">
<br></br>
できあがったのを確認したら、**村人に話しかけよう**

```blocks

let 開始位置: Position = null
let 作物 = 0
player.onChat("set", function () {
    開始位置 = player.position()
    作物 = CROPS
})
player.onChat("run", function () {
    for (let index = 0; index < 2; index++) {
        blocks.fill(
        FARMLAND,
        positions.add(
        開始位置,
        pos(1, -1, 1)
        ),
        positions.add(
        開始位置,
        pos(9, -1, 9)
        ),
        FillOperation.Replace
        )
        blocks.place(WATER, positions.add(
        開始位置,
        pos(5, -1, 5)
        ))
        blocks.fill(
        作物,
        positions.add(
        開始位置,
        pos(1, 0, 1)
        ),
        positions.add(
        開始位置,
        pos(9, 0, 9)
        ),
        FillOperation.Replace
        )
        開始位置 = positions.add(
        開始位置,
        pos(9, 0, 1)
        )
        作物 = CARROTS
    }
})

```
