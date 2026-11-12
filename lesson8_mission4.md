# ゲームをおもしろくしよう！

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
    ポイント = 0
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.timeSet(gameplay.time(NIGHT))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "ポイント：" + ポイント)
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "ポイント：" + ポイント)
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
        if (blocks.testForBlock(STONE_BRICKS, pos(0, 2, 0))) {
            blocks.replace(
            AIR,
            STONE_BRICKS,
            pos(0, 2, 0),
            pos(0, 2, 0)
            )
        }
        if (blocks.testForBlock(EMERALD_BLOCK, pos(0, 2, 0))) {
            ポイント += 1
            blocks.replace(
            AIR,
            EMERALD_BLOCK,
            pos(0, 2, 0),
            pos(0, 2, 0)
            )
        }
    }
})
let ランダムな数 = 0
let ポイント = 0
let スイッチ = false
スイッチ = false
ポイント = 0

```


```template

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

## ゲームをおもしろくしよう！@unplugged
ゲームをもっとおもしろくしよう！



## 例①ブロックをこわせるようにしよう！
プレイヤーが下からジャンプしたら、**石レンガ**をこわせるようにしよう！


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
        if (blocks.testForBlock(STONE_BRICKS, pos(0, 2, 0))) {
            blocks.replace(
            AIR,
            STONE_BRICKS,
            pos(0, 2, 0),
            pos(0, 2, 0)
            )
        }
    }
})
let ランダムな数 = 0
let ポイント = 0
let スイッチ = false
スイッチ = false





```



## 例②ポイントをつけよう
プレイヤーが**エメラルドブロック**をこわしたら**ポイント**をふやし、ゴールしたときやゲームオーバーのときにポイントを表示しよう！

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
    ポイント = 0
    スイッチ = true
    player.teleport(world(109, 104, -708))
    gameplay.timeSet(gameplay.time(NIGHT))
    gameplay.title(mobs.target(LOCAL_PLAYER), "スタート！", "")
    while (スイッチ == true) {
        mobs.applyEffect(JUMP_BOOST, mobs.target(LOCAL_PLAYER), 10, 3)
        if (blocks.testForBlock(RED_CONCRETE, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゴール！", "ポイント：" + ポイント)
            gameplay.timeSet(gameplay.time(MIDDAY))
            mobs.clearEffect(mobs.target(LOCAL_PLAYER))
            mobs.kill(
            mobs.entitiesByType(mobs.monster(ZOMBIE))
            )
            player.teleport(world(96, 104, -704))
        }
        if (blocks.testForBlock(LAVA, pos(0, -1, 0))) {
            スイッチ = false
            gameplay.title(mobs.target(LOCAL_PLAYER), "ゲームオーバー・・・", "ポイント：" + ポイント)
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
        if (blocks.testForBlock(STONE_BRICKS, pos(0, 2, 0))) {
            blocks.replace(
            AIR,
            STONE_BRICKS,
            pos(0, 2, 0),
            pos(0, 2, 0)
            )
        }
        if (blocks.testForBlock(EMERALD_BLOCK, pos(0, 2, 0))) {
            ポイント += 1
            blocks.replace(
            AIR,
            EMERALD_BLOCK,
            pos(0, 2, 0),
            pos(0, 2, 0)
            )
        }
    }
})
let ランダムな数 = 0
let ポイント = 0
let スイッチ = false
スイッチ = false
ポイント = 0

```
