# Tutorial Matrix Wiring

```package
neopixelExtended=github:PasAlt/pxt-neopixel-matrix-extension
```

## Introduction

In this tutorial you will learn how to determine the wiring of a NeoPixel matrix

If you have never used a NeoPixel and don't know how to connect it then please start with the [beginner tutorial](https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial).

## Matrix wiring

A NeoPixel Matrix is composed of multiple NeoPixels wired together in series on a two dimensional grid. 

NeoPixel matrices are in almost all cases wired in rows. Those rows can then be wired in different ways. 

The most important difference is in which direction the first row starts. Either from left to right or from right to left.

### Additional information

In most cases the rows are connected like a "snake" meaning that even rows run in one direction and odd rows run in the other direction. 

### ~ alert

In some rare cases rows are connected that each row starts in the same direction. This wiring is unfortunately currently not supported in this extension.

### ~

## Set up a rainbow pattern

We are now setting the Micro:Bit up to show a rainbox pattern on the NeoPixel matrix. We will use that pattern to determine the start and direction of the wiring. Where the first NeoPixel will have a red color and the last NeoPixel will be a violet color. 

Open the NeoPixel tab on the left side. Then select the first element called **``set strip to..``** and drag it into the **``on start``** block. 

Set the number of NeoPixels to the number of NeoPixels on your matrix, e.g. for a five times 5 matrix it would be 25 (see example).

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
```

## Use rainbox pattern

Drag the block **``||neopixelExtended:show rainbow||``** from the advanced block in the NeoPixel tab into the Editor. Set it below the previous block. Set starting value to 1 (red) and end value to 270 (violet).

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
strip.showRainbow(1, 270)
```

## Show matrix wiring with rainbow pattern
Now connect your Micro:Bit with your Computer and the NeoPixel matrix. Make sure that you connect the NeoPixel matrix on Pin 0. Then press "Download".

If you have never connected any NeoPixels to the Micro:Bit and need help then it is recommended to do the (NeoPixel Beginner Tutorial)[https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial] first.

## Determine start of wiring
Look at your NeoPixel matrix and check where the first red NeoPixel is. This is the first NeoPixel and the start of the NeoPixel strip.

Write down the start position, eg. Top left, top right, bottom left or bottom right.

## Determine direction of wiring
Look at the NeoPixel next to your starting that is slightly more yellow. 

The direction from your starting NeoPixel to the slightly more yellow pixel is the wiring direction.

Write down the direction, eg. To the right, to the left, to the bottom or to the top.

## Select the right wiring command
Combine start and direction to one short sentence.

Open the tab "NeopixelExtended". Drag the **``||neopixelExtended:strip set Neopixel wiring||``** into the editor.

Select the start and direction that you determined from above.





