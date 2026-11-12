# テーマパークの入り口を作ろう！

```template

function ゲート下部を作る (開始位置: Position) {
    // 床をつくる
    blocks.fill(
    CHISELED_STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(21, -1, 5)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE,
    positions.add(
    開始位置,
    pos(2, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(20, 0, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE,
    positions.add(
    開始位置,
    pos(2, 0, 4)
    ),
    positions.add(
    開始位置,
    pos(20, 0, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE_GATE,
    positions.add(
    開始位置,
    pos(4, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(6, 0, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE_GATE,
    positions.add(
    開始位置,
    pos(4, 0, 4)
    ),
    positions.add(
    開始位置,
    pos(6, 0, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE_GATE,
    positions.add(
    開始位置,
    pos(16, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(18, 0, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    OAK_FENCE_GATE,
    positions.add(
    開始位置,
    pos(16, 0, 4)
    ),
    positions.add(
    開始位置,
    pos(18, 0, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WOODEN_PRESSURE_PLATE,
    positions.add(
    開始位置,
    pos(16, 0, 1)
    ),
    positions.add(
    開始位置,
    pos(18, 0, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WOODEN_PRESSURE_PLATE,
    positions.add(
    開始位置,
    pos(16, 0, 3)
    ),
    positions.add(
    開始位置,
    pos(18, 0, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WOODEN_PRESSURE_PLATE,
    positions.add(
    開始位置,
    pos(4, 0, 3)
    ),
    positions.add(
    開始位置,
    pos(6, 0, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    WOODEN_PRESSURE_PLATE,
    positions.add(
    開始位置,
    pos(4, 0, 5)
    ),
    positions.add(
    開始位置,
    pos(6, 0, 5)
    ),
    FillOperation.Replace
    )
    // 真ん中の小屋
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(9, 0, 1)
    ),
    positions.add(
    開始位置,
    pos(13, 0, 5)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(COBBLESTONE_WALL, 7),
    positions.add(
    開始位置,
    pos(9, 1, 1)
    ),
    positions.add(
    開始位置,
    pos(13, 2, 5)
    ),
    FillOperation.Replace
    )
    // 真ん中の小屋
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(10, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(12, 2, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS_PANE,
    positions.add(
    開始位置,
    pos(10, 1, 1)
    ),
    positions.add(
    開始位置,
    pos(12, 2, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS_PANE,
    positions.add(
    開始位置,
    pos(10, 1, 5)
    ),
    positions.add(
    開始位置,
    pos(12, 2, 5)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS_PANE,
    positions.add(
    開始位置,
    pos(9, 1, 2)
    ),
    positions.add(
    開始位置,
    pos(9, 2, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    GLASS_PANE,
    positions.add(
    開始位置,
    pos(13, 1, 2)
    ),
    positions.add(
    開始位置,
    pos(13, 2, 4)
    ),
    FillOperation.Replace
    )
    // 真ん中の小屋
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(9, 3, 1)
    ),
    positions.add(
    開始位置,
    pos(13, 3, 5)
    ),
    FillOperation.Replace
    )
    // 真ん中の小屋
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(10, 4, 2)
    ),
    positions.add(
    開始位置,
    pos(12, 4, 4)
    ),
    FillOperation.Replace
    )
    for (let index = 0; index < 2; index++) {
        mobs.spawn(VILLAGER, positions.add(
        開始位置,
        pos(11, 0, 3)
        ))
    }
}
function 塔の屋根をつくる (開始位置: Position) {
    for (let カウンター = 0; カウンター <= 4; カウンター++) {
        shapes.circle(
        ORANGE_CONCRETE,
        positions.add(
        開始位置,
        pos(4, 16 + カウンター, 4)
        ),
        5 - カウンター,
        Axis.Y,
        ShapeOperation.Replace
        )
    }
    // 屋根のさきっぽ
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(4, 21, 4)
    ),
    positions.add(
    開始位置,
    pos(4, 22, 4)
    ),
    FillOperation.Replace
    )
    // はた
    blocks.fill(
    BIRCH_FENCE,
    positions.add(
    開始位置,
    pos(4, 23, 4)
    ),
    positions.add(
    開始位置,
    pos(4, 27, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    ORANGE_WOOL,
    positions.add(
    開始位置,
    pos(5, 25, 4)
    ),
    positions.add(
    開始位置,
    pos(5, 27, 4)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    ORANGE_WOOL,
    positions.add(
    開始位置,
    pos(6, 25, 5)
    ),
    positions.add(
    開始位置,
    pos(6, 27, 5)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    ORANGE_WOOL,
    positions.add(
    開始位置,
    pos(7, 26, 6)
    ),
    positions.add(
    開始位置,
    pos(8, 27, 6)
    ),
    FillOperation.Replace
    )
    blocks.place(ORANGE_CONCRETE, positions.add(
    開始位置,
    pos(9, 27, 7)
    ))
}
function 塔の本体をつくる (開始位置: Position) {
    // 中心部分
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(7, 15, 7)
    ),
    FillOperation.Replace
    )
    // まんなかあたりのかざり
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(1, 6, 1)
    ),
    positions.add(
    開始位置,
    pos(7, 7, 7)
    ),
    FillOperation.Replace
    )
    // 窓
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(2, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(6, 15, 6)
    ),
    FillOperation.Replace
    )
    // 窓
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(4, 13, 1)
    ),
    positions.add(
    開始位置,
    pos(4, 14, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(4, 13, 7)
    ),
    positions.add(
    開始位置,
    pos(4, 14, 7)
    ),
    FillOperation.Replace
    )
    // 角のかざり
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(1, 8, 1)
    ),
    positions.add(
    開始位置,
    pos(2, 15, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(1, 8, 6)
    ),
    positions.add(
    開始位置,
    pos(2, 15, 7)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(6, 8, 1)
    ),
    positions.add(
    開始位置,
    pos(7, 15, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(6, 8, 6)
    ),
    positions.add(
    開始位置,
    pos(7, 15, 7)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(2, 8, 2)
    ),
    positions.add(
    開始位置,
    pos(2, 15, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(2, 8, 6)
    ),
    positions.add(
    開始位置,
    pos(2, 15, 6)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(6, 8, 2)
    ),
    positions.add(
    開始位置,
    pos(6, 15, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(6, 8, 6)
    ),
    positions.add(
    開始位置,
    pos(6, 15, 6)
    ),
    FillOperation.Replace
    )
    blocks.place(AIR, positions.add(
    開始位置,
    pos(1, 7, 1)
    ))
    blocks.place(AIR, positions.add(
    開始位置,
    pos(1, 7, 7)
    ))
    blocks.place(AIR, positions.add(
    開始位置,
    pos(7, 7, 1)
    ))
    blocks.place(AIR, positions.add(
    開始位置,
    pos(7, 7, 7)
    ))
    // 下側のかざり
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(2, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(6, 6, 0)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(2, 0, 8)
    ),
    positions.add(
    開始位置,
    pos(6, 6, 8)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(0, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(0, 6, 6)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(8, 0, 2)
    ),
    positions.add(
    開始位置,
    pos(8, 6, 6)
    ),
    FillOperation.Replace
    )
    // 入口
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(3, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(5, 1, 0)
    ),
    FillOperation.Replace
    )
    blocks.place(ORANGE_CONCRETE, positions.add(
    開始位置,
    pos(4, 2, 0)
    ))
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(4, 0, 0)
    ),
    positions.add(
    開始位置,
    pos(4, 1, 1)
    ),
    FillOperation.Replace
    )
    // 入口
    blocks.fill(
    ORANGE_CONCRETE,
    positions.add(
    開始位置,
    pos(3, 0, 8)
    ),
    positions.add(
    開始位置,
    pos(5, 1, 8)
    ),
    FillOperation.Replace
    )
    blocks.place(ORANGE_CONCRETE, positions.add(
    開始位置,
    pos(4, 2, 8)
    ))
    blocks.fill(
    AIR,
    positions.add(
    開始位置,
    pos(4, 0, 7)
    ),
    positions.add(
    開始位置,
    pos(4, 1, 8)
    ),
    FillOperation.Replace
    )
}
function 通路とはしごをつくる () {
    // はしご(西)
    blocks.fill(
    blocks.blockWithData(LADDER, 5),
    world(-16, -60, 14),
    world(-16, -50, 14),
    FillOperation.Replace
    )
    // はしご(東)
    blocks.fill(
    blocks.blockWithData(LADDER, 4),
    world(16, -60, 14),
    world(16, -50, 14),
    FillOperation.Replace
    )
    // 通路(西)
    blocks.fill(
    STONE_BRICKS,
    world(-18, -50, 11),
    world(-18, -49, 17),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(-18, -49, 12),
    world(-18, -49, 16),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    world(-17, -50, 16),
    world(-16, -49, 17),
    FillOperation.Replace
    )
    blocks.place(AIR, world(-17, -49, 16))
    blocks.fill(
    STONE_BRICKS,
    world(-17, -50, 11),
    world(-16, -49, 12),
    FillOperation.Replace
    )
    blocks.place(AIR, world(-17, -49, 12))
    blocks.fill(
    STONE_BRICKS,
    world(-18, -53, 12),
    world(-18, -51, 16),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 6),
    world(-19, -51, 11),
    world(-18, -51, 11),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 7),
    world(-19, -51, 17),
    world(-18, -51, 17),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 2),
    world(-19, -60, 11),
    world(-18, -60, 11),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 3),
    world(-19, -60, 17),
    world(-18, -60, 17),
    FillOperation.Replace
    )
    // 通路(西)
    blocks.fill(
    STONE_BRICKS,
    world(18, -50, 11),
    world(18, -49, 17),
    FillOperation.Replace
    )
    blocks.fill(
    AIR,
    world(18, -49, 12),
    world(18, -49, 16),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    world(16, -50, 16),
    world(17, -49, 17),
    FillOperation.Replace
    )
    blocks.place(AIR, world(17, -49, 16))
    blocks.fill(
    STONE_BRICKS,
    world(16, -50, 11),
    world(17, -49, 12),
    FillOperation.Replace
    )
    blocks.place(AIR, world(17, -49, 12))
    blocks.fill(
    STONE_BRICKS,
    world(18, -53, 12),
    world(18, -51, 16),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 6),
    world(18, -51, 11),
    world(19, -51, 11),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 7),
    world(18, -51, 17),
    world(19, -51, 17),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 2),
    world(18, -60, 11),
    world(19, -60, 11),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 3),
    world(18, -60, 17),
    world(19, -60, 17),
    FillOperation.Replace
    )
}
player.onChat("run", function () {
    塔の本体をつくる(作り始める位置)
    塔の屋根をつくる(作り始める位置)
    ゲート上部をつくる(positions.add(
    作り始める位置,
    pos(7, 13, 2)
    ))
    塔の本体をつくる(positions.add(
    作り始める位置,
    pos(28, 0, 0)
    ))
    塔の屋根をつくる(positions.add(
    作り始める位置,
    pos(28, 0, 0)
    ))
    通路とはしごをつくる()
    ゲート下部を作る(positions.add(
    作り始める位置,
    pos(7, 0, 1)
    ))
})
function ゲート上部をつくる (開始位置: Position) {
    // 本体
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, 1, 1)
    ),
    positions.add(
    開始位置,
    pos(21, 1, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(8, 2, 1)
    ),
    positions.add(
    開始位置,
    pos(14, 2, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, 0, 1)
    ),
    positions.add(
    開始位置,
    pos(7, 0, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, -1, 2)
    ),
    positions.add(
    開始位置,
    pos(5, -1, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(17, -1, 2)
    ),
    positions.add(
    開始位置,
    pos(21, -1, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(1, -2, 2)
    ),
    positions.add(
    開始位置,
    pos(3, -2, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(19, -2, 2)
    ),
    positions.add(
    開始位置,
    pos(21, -2, 2)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    STONE_BRICKS,
    positions.add(
    開始位置,
    pos(15, 0, 1)
    ),
    positions.add(
    開始位置,
    pos(21, 0, 3)
    ),
    FillOperation.Replace
    )
    // かざり
    blocks.fill(
    STONE_BRICK_STAIRS,
    positions.add(
    開始位置,
    pos(7, 2, 1)
    ),
    positions.add(
    開始位置,
    pos(7, 2, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 1),
    positions.add(
    開始位置,
    pos(15, 2, 1)
    ),
    positions.add(
    開始位置,
    pos(15, 2, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 6),
    positions.add(
    開始位置,
    pos(8, 0, 1)
    ),
    positions.add(
    開始位置,
    pos(14, 0, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 7),
    positions.add(
    開始位置,
    pos(8, 0, 3)
    ),
    positions.add(
    開始位置,
    pos(14, 0, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 6),
    positions.add(
    開始位置,
    pos(1, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(5, -1, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 6),
    positions.add(
    開始位置,
    pos(17, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(21, -1, 1)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 7),
    positions.add(
    開始位置,
    pos(1, -1, 3)
    ),
    positions.add(
    開始位置,
    pos(5, -1, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 7),
    positions.add(
    開始位置,
    pos(17, -1, 3)
    ),
    positions.add(
    開始位置,
    pos(21, -1, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 5),
    positions.add(
    開始位置,
    pos(6, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(6, -1, 3)
    ),
    FillOperation.Replace
    )
    blocks.fill(
    blocks.blockWithData(STONE_BRICK_STAIRS, 4),
    positions.add(
    開始位置,
    pos(16, -1, 1)
    ),
    positions.add(
    開始位置,
    pos(16, -1, 3)
    ),
    FillOperation.Replace
    )
    blocks.place(blocks.blockWithData(STONE_BRICK_STAIRS, 5), positions.add(
    開始位置,
    pos(4, -2, 2)
    ))
    blocks.place(blocks.blockWithData(STONE_BRICK_STAIRS, 5), positions.add(
    開始位置,
    pos(1, -3, 2)
    ))
    blocks.place(blocks.blockWithData(STONE_BRICK_STAIRS, 4), positions.add(
    開始位置,
    pos(18, -2, 2)
    ))
    blocks.place(blocks.blockWithData(STONE_BRICK_STAIRS, 4), positions.add(
    開始位置,
    pos(21, -3, 2)
    ))
}
let 作り始める位置: Position = null
作り始める位置 = world(-18, -60, 10)





```

## テーマパークの入り口をつくろう！ @unplugged
プログラミングでテーマパークの入り口を出してみよう！！



## 実行しよう！
今回は、あらかじめ**テーマパークの入り口をつくるプログラム**が作ってあります
さっそく実行してみましょう！
<br></br>
<img height="50%" width="50%" src="https://vcode-esia.com/images_for_world_data/school/1st/execute.gif">
<br></br>
ゲーム画面にもどったら、チャットでrunと入力してみよう！
入り口が出来上がったら、**中に入って作品をつくりはじめよう！**
