# モササウルスをつかまえよう！

```blocks

function すいそうを作る (範囲の始まり: Position, 範囲の終わり: Position) {
    player.say(範囲の始まり)
    player.say(範囲の終わり)
    blocks.fill(
    GLASS,
    positions.add(
    範囲の始まり,
    pos(-10, 0, -10)
    ),
    positions.add(
    範囲の終わり,
    pos(10, 0, 10)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    positions.add(
    範囲の始まり,
    pos(-9, 0, -9)
    ),
    positions.add(
    範囲の終わり,
    pos(9, -1, 9)
    ),
    FillOperation.Replace
    )
}
player.onItemInteracted(STICK, function () {
    範囲の始まり = positions.add(
    player.position(),
    pos(0, -1, 0)
    )
    範囲の終わり = player.position()
    while (blocks.testForBlock(WATER, 範囲の始まり)) {
        範囲の始まり = positions.add(
        範囲の始まり,
        pos(0, -1, 0)
        )
    }
    すいそうを作る(範囲の始まり, 範囲の終わり)
})
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
mobs.give(
mobs.target(LOCAL_PLAYER),
BOAT,
1
)




```


```template

function すいそうを作る (開始位置: Position) {
}
player.onItemInteracted(STICK, function () {
    範囲の始まり = positions.add(
    player.position(),
    pos(0, -1, 0)
    )
    範囲の終わり = player.position()
    while (blocks.testForBlock(WATER, 範囲の始まり)) {
        範囲の始まり = positions.add(
        範囲の始まり,
        pos(0, -1, 0)
        )
    }
    すいそうを作る(範囲の始まり, 範囲の終わり)
})
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
mobs.give(
mobs.target(LOCAL_PLAYER),
BOAT,
1
)

```

## モササウルスをつかまえよう！@unplugged
！関数で水槽を作ってモササウルスをつかまえよう！
<n></n>
<img style="display: block; margin: auto;" height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete4.gif">



## モササウルスをつかまえよう！
ガラスでかこんで、モササウルスをつかまえよう！
モササウルスはとてもきけんな恐竜です・・・万全のじゅんびをしよう！
<br></br>
<img width="100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme4/Lesson6/L6_complete4.gif">



## ガラスで囲むプログラム
プログラムはとちゅうまで用意してあります
・**棒**をつかったとき：``||variables.範囲の始まり||``には、**プレイヤーの下にある地面の場所の座標**、``||variables.範囲の終わり||``には、**プレイヤーの場所の座標**が入る
``||functions.すいそうを作る||``の中に、変数に入った座標を使って**ガラス**と**空気**をならべ、プレイヤーを中心としてすいそうがつくられるようにしよう！

```blocks

function すいそうを作る (範囲の始まり: Position, 範囲の終わり: Position) {
    player.say(範囲の始まり)
    player.say(範囲の終わり)
    blocks.fill(
    GLASS,
    positions.add(
    範囲の始まり,
    pos(-10, 0, -10)
    ),
    positions.add(
    範囲の終わり,
    pos(10, 0, 10)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WATER,
    positions.add(
    範囲の始まり,
    pos(-9, 0, -9)
    ),
    positions.add(
    範囲の終わり,
    pos(9, -1, 9)
    ),
    FillOperation.Replace
    )
}
player.onItemInteracted(STICK, function () {
    範囲の始まり = positions.add(
    player.position(),
    pos(0, -1, 0)
    )
    範囲の終わり = player.position()
    while (blocks.testForBlock(WATER, 範囲の始まり)) {
        範囲の始まり = positions.add(
        範囲の始まり,
        pos(0, -1, 0)
        )
    }
    すいそうを作る(範囲の始まり, 範囲の終わり)
})
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
mobs.give(
mobs.target(LOCAL_PLAYER),
STICK,
1
)
mobs.give(
mobs.target(LOCAL_PLAYER),
BOAT,
1
)



```
