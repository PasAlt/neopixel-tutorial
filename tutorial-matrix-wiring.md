# Tutorial Matrix Wiring

```package
neopixel=github:PasAlt/pxt-neopixel-matrix-extension
```

## Introduction
A NeoPixel Matrix is composed of multiple NeoPixels wired together in series on a two dimensional grid. 

They are in almost all cases wired in rows. Those rows can then be wired in different ways. 

The most important difference is in which direction the first row starts. Either from left to right or from right to left.

### Additional information
In most cases the rows are connected like a "snake" meaning that even rows run in one direction and odd rows run in the other direction. 

In some rare cases rows are connected that each row starts in the same direction. This wiring is unfortunately currently not supported in this extension.

## Set up rainbow pattern
We are now setting the Micro:Bit up to show a rainbox pattern on the NeoPixel matrix. We will use that pattern to determine that start and direction of the wiring. Where the first NeoPixel will have a red color and the last NeoPixel will be a violet color. 

Open the NeoPixel tab on the left side. Then select the first element called **``set strip to..``** and drag it into the **``on start``** block. 

### Create NeoPixel driver
Set the number of NeoPixels to the number of NeoPixels on your matrix, e.g. for a five times 5 matrix it would be 25.

### Use rainbox pattern
Drag the block **``show rainbow``** from the advanced block in the NeoPixel tab into the Editor. Set it below the previous block. Set starting value to 1 (red) and end value to 270 (violet).

```blocks
let strip = neopixel.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
strip.showRainbow(1, 270)
```

## Show matrix wiring with rainbow pattern
Now connect your Micro:Bit with your Computer and the NeoPixel matrix. Make sure that you connect the NeoPixel matrix on Pin 0. If you have never connected any NeoPixels to the Micro:Bit and need help then it is recommended to do the (NeoPixel Beginner Tutorial)[https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial] first.

