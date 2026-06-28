# Tutorial NeoPixel matrix

```package
neopixel=github:PasAlt/pxt-neopixel-matrix-extension
```

## Connect NeoPixel matrix with Micro:Bit

In this tutorial you will learn how to use the matrix blocks in the NeoPixel extension.

You will create a matrix that changes between the letters "O" and "K" each second. 

Connect your NeoPixel matrix with the Micro:Bit on Pin 0.

If you have never used a NeoPixel and don't know how to connect it then please start with the [beginner tutorial](https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial).

## Initialize NeoPixel Object

Open the NeoPixel tab on the left side. Then select the first element called **``set strip to..``** and drag it into the **``on start``** block. 

Your NeoPixel constists of five times five elements therefore 25 elements overall. You need to change the number of leds to 25 NeoPixels by clicking in it.

Leave the rest as it is.

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
```

## Set the matrix colors
We will use the **``forever``** block to change between two screens. 

To let the NeoPixel matrix glow you will use the **``set Neopixel 5x5``** block.

Drag the ``set Neopixel 5x5`` into the ``forever`` forever block.

Change the colors on the matrix by clicking on the colors. Change the colors that it forms an "O".

Running this command will store the colors into a buffer. The NeoPixel matrix will not yet glow when you press download.

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
basic.forever(function () {
    strip.setMatrix25(
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700)
    )
})
```

## Show the matrix
We are now setting commands to show the colors on the NeoPixel.

Drag the block **``show``** below the current block. 

Run the programm by pressing the download button. You should see your NeoPixel glow up with your colors. 

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
basic.forever(function () {
    strip.setMatrix25(
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700)
    )
    strip.show()
})
```

## Pause
To be able to change between two different images we need to keep each image for a second. We will use the **``pause``** command for that.

Drag the block **``pause``** below the ``show`` block and set it to 1000 miliseconds.

When you run the program you will not see any difference to before. This is because after one second the same image is shown again. We will need to add another image.

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
basic.forever(function () {
    strip.setMatrix25(
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700)
    )
    strip.show()
    basic.pause(1000)
})
```

## Repeat previous blocks

To change between two immages you will need to add the same blocks **``set Neopixel 5x5``**, **``show``** and **``pause``** again.

Then change the colors in the second ``set Neopixel 5x5`` block that it represents a K.

Run the program by pressing download.

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
basic.forever(function () {
    strip.setMatrix25(
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700)
    )
    strip.show()
    basic.pause(1000)
    strip.setMatrix25(
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xff0000, 0xFFD700),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xFFD700, 0xff0000),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xE60026, 0xff0000),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xFFD700, 0xff0000),
    neopixel.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xff0000, 0xFFD700)
    )
    strip.show()
    basic.pause(1000)
})
```

