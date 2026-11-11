# フェンスと生き物を出そう！

```blocks

let フェンスの種類 = 0
let 生き物の種類 = 0
let 生き物の数 = 0
player.onChat("run", function (num1) {
    if (num1 == 0) {
        フェンスの種類 = OAK_FENCE
        生き物の種類 = COW
        生き物の数 = 5
    } else if (num1 == 1) {
        フェンスの種類 = ACACIA_FENCE
        生き物の種類 = PIG
        生き物の数 = 7
    } else {
        フェンスの種類 = SPRUCE_FENCE
        生き物の種類 = CHICKEN
        生き物の数 = 10
    }
    blocks.fill(
    フェンスの種類,
    pos(1, 0, 1),
    pos(5, 0, 11),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    pos(2, 0, 2),
    pos(4, 0, 10),
    FillOperation.Replace
    )
    for (let index = 0; index < 生き物の数; index++) {
        mobs.spawn(生き物の種類, pos(3, 0, 5))
    }
})

```

```template

let フェンスの種類 = 0
let 生き物の種類 = 0
let 生き物の数 = 0
player.onChat("run", function (num1) {
    if (num1 == 0) {

    } else if (num1 == 1) {

    } else {

    }

})


```

## フェンスと生き物を出そう！ @unplugged
変数を使って、フェンスと生き物を出そう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete1.png">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・3種類のフェンスと生き物を出そう
①**オークのフェンス**の中に**牛を5頭**スポーンさせる
②**アカシアのフェンス**の中に**ブタを7ひき**スポーンさせる
②**トウヒのフェンス**の中に**ニワトリを10羽**スポーンさせる
・フェンスの大きさは、**東に5ブロック**、**南に11ブロック**
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_top_view1.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
変数``||variables.フェンスの種類||``、``||variables.生き物の種類||``、``||variables.生き物の数||``があります。
これと**条件分岐**を組み合わせて、チャットで「**run 0**」、「**run 1**」、「**run 2**」と入力したときにプログラムが実行されるようにしてみましょう！
フェンスは、**まず範囲内に並べてから中をくりぬく**とよさそうです！
<br></br>
むずかしいときは、**Theme2 Lesson5**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson5/L5_complete1.png">
<br></br>
できあがったのを確認したら、**村人に話しかけよう**

```blocks

let フェンスの種類 = 0
let 生き物の種類 = 0
let 生き物の数 = 0
player.onChat("run", function (num1) {
    if (num1 == 0) {
        フェンスの種類 = OAK_FENCE
        生き物の種類 = COW
        生き物の数 = 5
    } else if (num1 == 1) {
        フェンスの種類 = ACACIA_FENCE
        生き物の種類 = PIG
        生き物の数 = 7
    } else {
        フェンスの種類 = SPRUCE_FENCE
        生き物の種類 = CHICKEN
        生き物の数 = 10
    }
    blocks.fill(
    フェンスの種類,
    pos(1, 0, 1),
    pos(5, 0, 11),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    pos(2, 0, 2),
    pos(4, 0, 10),
    FillOperation.Replace
    )
    for (let index = 0; index < 生き物の数; index++) {
        mobs.spawn(生き物の種類, pos(3, 0, 5))
    }
})

```
