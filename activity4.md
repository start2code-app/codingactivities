# Activity 4

## Step 1

Step 1
Declare 3 Variables ``||variables:game||``,``||variables:delay||``,``||variables:player||`` and add the following blocks 

```blocks
let delay = 1000
player = game.createSprite(2, 4)
game.setScore(0)
```

## Step 2 

Step 2

```blocks
let player: game.LedSprite = null
input.onButtonPressed(Button.A, function () {
    player.move(-1)
})

input.onButtonPressed(Button.B, function () {
    player.move(1)
})
```

## Step 3

```blocks

let fruit: game.LedSprite = null

basic.forever(function () {
    fruit = game.createSprite(randint(0, 4), 0)
    basic.pause(delay)
    while (fruit.get(LedSpriteProperty.Y) < 4) {
        fruit.change(LedSpriteProperty.Y, 1)
        basic.pause(delay)
    }


})

```

## Step 4

Add the following to the ``||basic:forever||`` block

```blocks
basic.forever(function () {
  let player: game.LedSprite = null 
  let fruit: game.LedSprite = null 

    if (player.isTouching(fruit)) {
        game.addScore(1)
    } else {
        game.gameOver()
    }

})

```

## Step 5

Add the following to the ``||basic:forever||`` block
```blocks

let fruit: game.LedSprite = null

basic.forever(function () {

    fruit.set(LedSpriteProperty.Brightness, 0)
    delay = delay - delay / 10
})

```
