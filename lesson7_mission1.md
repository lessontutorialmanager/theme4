# きほんのルールを作ろう！

```blocks

player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "")
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "")
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            player.teleport(world(96, 104, -704))
        }
    }
})
let スイッチ = false
スイッチ = false


```

```template
let スイッチ = false
スイッチ = false

player.onChat("run", function () {

})


```

## きほんのルールを作ろう！ @unplugged
スタートからゴールまでのきほんのルールを作ろう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete1.gif">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・変数``||variables.スイッチ||``を作って、チャットコマンドで``||player.run||``と入力したら、**真(しん)**にして、プレイヤーを``||positions.ワールド(109, 104, -708)||``へ**テレポート**するようにしよう！
``||variables.スイッチ||``が**真**のあいだ、
②プレイヤーに**持続(じぞく)時間10秒(びょう)**、**効果(こうか)レベル3**の**跳躍力(ちょうやくりょく)上昇**の``||mobs.特殊効果||``がつくようにする
②プレイヤーの足元に**赤色のコンクリートブロック**があるとき、``||variables.スイッチ||``を**偽(ぎ)**にして、**ゴール！**と**タイトルを表示**して、``||mobs.すべてのステータス効果を消去||``し、プレイヤーを``||positions.ワールド(96, 104, -704)||``へ**テレポート**する
②プレイヤーの足元に**マグマ**があるとき、``||variables.スイッチ||``を**偽(ぎ)**にして、**ゲームオーバー・・・**と**タイトルを表示**して、``||mobs.すべてのステータス効果を消去||``し、プレイヤーを``||positions.ワールド(96, 104, -704)||``へ**テレポート**する
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_flow1.png">



## プログラミングのヒント
下のヒントを参考にしてみよう！
``||loops.もし～ならくりかえし||``と、``||variables.スイッチ||``を組み合わせれば、スイッチが真のあいだくりかえすことができそうです！
プレイヤーの足元に何のブロックがあるか確認するには、``||blocks.～が(~0, ~-1, ~0)に存在する||``をつかって**条件分岐**しましょう。
<br></br>
むずかしいときは、**Theme2 Lesson2**や**Theme2 Lesson8**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete1.gif">
<br></br>
**ゴールにたどりつくまでプレイ**してみて、しくみができているのを確認したら**ぼうしをかぶった村人に話しかけよう**

```blocks

player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "")
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "")
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            player.teleport(world(96, 104, -704))
        }
    }
})
let スイッチ = false
スイッチ = false

```
