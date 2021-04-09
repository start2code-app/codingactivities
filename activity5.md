# Activity 5

## Step 1

Step 1
Declare 4 Variables ``||variables:ypos||``,``||variables:xpos||``,``||variables:shipxpos||``,``||variables:empty||`` and add the following blocks 

```blocks
let empty = 0
let shipxpos = 0
shipxpos = 2
let score = 0
led.setBrightness(100)
led.plot(shipxpos, 4)
```

## Step 2 

Step 2

```blocks
input.onButtonPressed(Button.A, function () {
    if (shipxpos > 0) {
        led.unplot(shipxpos, 4)
        shipxpos += -1
        led.plot(shipxpos, 4)
    }
})
input.onButtonPressed(Button.B, function () {
    if (shipxpos < 4) {
        led.unplot(shipxpos, 4)
        shipxpos += 1
        led.plot(shipxpos, 4)
    }
})
```

## Step 3

```blocks

basic.forever(function () {
    empty = randint(0, 4)
    for (let ypos = 0; ypos <= 4; ypos++) {

    }
    score += 1
})

```

## Step 4

Add the following inside the ``||loops:for loop||`` block

```blocks
basic.forever(function () {
        for (let xpos = 0; xpos <= 4; xpos++) {
            if (empty != xpos) {
                led.plot(xpos, ypos)
            }
        }
        basic.pause(300 - score)
})
```

## Step 5

Add the following inside the ``||loops:for loop||`` block
```blocks
basic.forever(function () {
        for (let xpos = 0; xpos <= 4; xpos++) {
            if (empty != xpos) {
                led.unplot(xpos, ypos)
            }
        }
})
```

## Step 6

Add the following inside the ``||loops:for loop||`` block
```blocks
basic.forever(function () {
        if (ypos == 4 && shipxpos != empty) {
            basic.showIcon(IconNames.No)
            basic.pause(2000)
            basic.showNumber(score)
            basic.clearScreen()
            score = -1
            shipxpos = 2
            led.plot(shipxpos, 4)
        }
})
```

