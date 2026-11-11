# 特殊効果をあたえよう！

```blocks

loops.forever(function () {
    if (スイッチ == true) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
        world(108, 104, -711),
        world(110, 114, -620)
        ))
        loops.pause(2000)
    }
})
player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.timeSet(gameplay.time(NIGHT))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
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
        if (blocks.testForBlock(DIAMOND_BLOCK, pos(0, -1, 0))) {
            ランダムな数 = randint(0, 2)
            if (ランダムな数 == 0) {
                mobs.applyEffect(STRENGTH, mobs.target(LOCAL_PLAYER), 30, 3)
            } else if (ランダムな数 == 1) {
                mobs.applyEffect(INVISIBILITY, mobs.target(LOCAL_PLAYER), 30, 3)
            } else if (ランダムな数 == 2) {
                mobs.applyEffect(SPEED, mobs.target(LOCAL_PLAYER), 30, 3)
            }
            loops.pause(10000)
        }
    }
})
let ランダムな数 = 0
let スイッチ = false
スイッチ = false



```

```template

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


## 特殊効果をあたえよう！ @unplugged
ダイヤモンドのブロックの上にのったときに、ランダムな特殊効果をあたえよう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete3.gif">



## 目標(もくひょう)
今回は、**いちから自分で考えてプログラミングしよう！**
・**ダイヤモンドのブロック**の上にのったときに、**ランダムな特殊効果**をあたえよう！
①持続時間**30** 効果レベル**3**の**攻撃力(こうげきりょく)上昇**
②持続時間**30** 効果レベル**3**の**透明(とうめい)**化
③持続時間**30** 効果レベル**3**の**移動速度(いどうそくど)**上昇
のどれかが、**10秒**おきに与えられるようにしよう！



## プログラミングのヒント
下のヒントを参考にしてみよう！
ランダムに特殊効果を与えるには、``||variables.ランダムな数||``を作って**乱数**を入れ、``||variables.ランダムな数||``に入った数によって**条件分岐**しましょう。
<br></br>
むずかしいときは、**Theme3 Lesson11**を復習してみよう！



## 実行しよう！
プログラミングができあがったら、▶ボタンを押(お)して実行しよう
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、思った通りにプログラムが動くか試してみよう！
うまくいかなかったときは、どこが良くなかったのか、自分のプログラムを見なおして何度でもちょうせんしてみよう
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson7/L7_complete3.gif">
<br></br>
**ゴールにたどりつくまでプレイ**してみて、特殊効果がつくのを確認したら**ぼうしをかぶった村人に話しかけよう**

```blocks

loops.forever(function () {
    if (スイッチ == true) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
        world(108, 104, -711),
        world(110, 114, -620)
        ))
        loops.pause(2000)
    }
})
player.onChat("run", function () {
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.timeSet(gameplay.time(NIGHT))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
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
        if (blocks.testForBlock(DIAMOND_BLOCK, pos(0, -1, 0))) {
            ランダムな数 = randint(0, 2)
            if (ランダムな数 == 0) {
                mobs.applyEffect(STRENGTH, mobs.target(LOCAL_PLAYER), 30, 3)
            } else if (ランダムな数 == 1) {
                mobs.applyEffect(INVISIBILITY, mobs.target(LOCAL_PLAYER), 30, 3)
            } else if (ランダムな数 == 2) {
                mobs.applyEffect(SPEED, mobs.target(LOCAL_PLAYER), 30, 3)
            }
            loops.pause(10000)
        }
    }
})
let ランダムな数 = 0
let スイッチ = false
スイッチ = false

```
