# ゾンビをスポーンさせよう！

```blocks

loops.forever(function () {
    if (スイッチ == true) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
        world(108, 104, -711),
        world(110, 114, -620)
        ))
        loops.pause(3000)
    }
})
player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    gameplay.timeSet(gameplay.time(MIDNIGHT))
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "")
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "")
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
    }
})
let スイッチ = false
スイッチ = false


```

```template

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


## ゾンビをスポーンさせよう！ @unplugged
ゲーム中、ゾンビをスポーンさせよう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete2.gif">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・ゲーム中、**ゾンビをスポーン**させよう！
・``||loops.ずっと||``と**条件分岐**を使って、ゲーム中、``||positions.ワールド(108, 104, -711)||``から``||positions.ワールド(110, 114, -620)||``の間の**ランダムな位置**に、**3秒**ごとに**ゾンビをスポーン**させる
・ゲームが始まったら、ゾンビが燃(も)えないように、**ゲーム内の時刻を**``||gameplay.真夜中||``にする
・プレイヤーがゴールしたときや、マグマに落ちたとき、**ゲーム内の時刻を**``||gameplay.正午||``にして、``||mobs.すべてのゾンビを死亡||``させる



## プログラミングのヒント
下のヒントを参考にしてみよう！
3秒ごとにゾンビをスポーンさせるには、``||loops.一時停止(ミリ秒) 3000||``を使いましょう。
ゾンビを死亡させるには、``||mobs.一番近いプレーヤー(@p) を死亡させる||``と、``||mobs.すべての生き物||``、``||mobs.モンスター||``の3つを組み合わせましょう！
<br></br>
むずかしいときは、**Theme2 Lesson10**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete2.gif">
<br></br>
**ゴールにたどりつくまでプレイ**してみて、真夜中になってゾンビがスポーンするのを確認したら**ぼうしをかぶった村人に話しかけよう**

```blocks

loops.forever(function () {
    if (スイッチ == true) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
        world(108, 104, -711),
        world(110, 114, -620)
        ))
        loops.pause(3000)
    }
})
player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    gameplay.timeSet(gameplay.time(MIDNIGHT))
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "")
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "")
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
    }
})
let スイッチ = false
スイッチ = false


```
