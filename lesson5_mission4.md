# 村をさらに発展させよう！



```template

let フェンスの種類 = 0
let 生き物の種類 = 0
let 生き物の数 = 0
let 開始位置: Position = null
let 作物 = 0
let 範囲の終わり: Position = null
let 範囲の始まり: Position = null
範囲の始まり = world(137, 63, -341)
範囲の終わり = world(145, 63, -337)
player.onChat("run1", function (num1) {
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
player.onChat("set", function () {
    開始位置 = player.position()
    作物 = CROPS
})
player.onChat("run2", function () {
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
player.onChat("run3", function () {
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

```

## 村をさらに発展させよう！@unplugged
工夫して村をもっと発展させよう！


## 例①
フェンスの種類と生き物の種類をふやそう！また、フェンスの中に入れるように**フェンスゲート**をとりつけよう！



## 例➁
畑に植える作物の種類をふやそう！また、畑の広さを変えられるようにしよう！



## 例③
冒険しやすくするために、**ダイヤモンドのブロック**と**ビーコン**を並べられるようにしよう！

```blocks

player.onChat("build", function () {
    blocks.fill(
    DIAMOND_BLOCK,
    pos(1, 0, 1),
    pos(3, 0, 3),
    FillOperation.Replace
    )
    blocks.place(BEACON, pos(2, 1, 2))
})


```
