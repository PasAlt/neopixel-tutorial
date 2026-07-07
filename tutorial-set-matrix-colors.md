# NeoPixel Set Single Matrix Colors Tutorial

```package
neopixel-extended=github:PasAlt/pxt-neopixel-matrix-extension
```

## Introduction

In this tutorial you will learn how to set up a NeoPixel driver for a 5x5 matrix that makes individual NeoPixels in the matrix one after another.

The end result will draw a diagonal line from the top left to the bottom right.

## Connect your micro:bit with your NeoPixel matrix

Connect your NeoPixel matrix with the micro:bit on Pin 0.

If you have never used a NeoPixel and don't know how to connect it then please start with the [beginner tutorial](https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial).

## Set up driver

At first you have to setup the NeoPixel driver. 

Drag the block **``||neopixelExtended:set strip||``** into the editor. 

As we want to setup a 5x5-Matrix set the number of NeoPixels to 25. 

Set the format appropriatly to the format of the NeoPixels in front of you. In most cases it will be **``||RGB (GRB format)||``** 

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
```

## Set up matrix wiring
NeoPixel can be wired in different ways. 

Drag the block **``||neopixelExtended:set NeoPixel matrix wiring||``** into the editor. Set the fitting wiring.

If you don't know how to set up correctly then check the tutorial on [how to matrix set up wiring](https://makecode.microbit.org/#tutorial:github:pasalt/neopixel-tutorial/tutorial-matrix-wiring)

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
strip.setMatrixWiring(neopixelExtended.MatrixDirection.LeftTopToTheRight)
```

## Set up matrix width and height
To be able to change individual NeoPixels we need to tell the driver the width and the height of the matrix. Otherwise it will throw an error, when we are trying make an individual NeoPixel glow.

In our case this will be a width of 5 and a height of 5.

Drag the block Drag the block **``||neopixelExtended:set width||``** into the editor and set width to 5.

Drag the block Drag the block **``||neopixelExtended:set height|``** into the editor and set width to 5.

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
strip.setMatrixWiring(neopixelExtended.MatrixDirection.LeftTopToTheRight)
strip.setMatrixWidth(5)
strip.setMatrixHeight(5)
```

## What you achieved @showdialog
You have now fully set up your NeoPixel driver by telling it the number of NeoPixels in the matrix (25), the matrix wiring and the size (width: 5, height: 5). In the next step we will learn how to address single NeoPixels in a matrix.

## Addressing individual NeoPixels
To address a NeoPixel you have to tell the driver in which row and in which column the NeoPixel can be found.

The vertical position, the row number, is in many cases abbreviated as x. The horizontal position, the column number, is in many cases abbreviated as y.

A bit peculiar is that the first row is 0 (instead of 1), the second is 1 (instead of 2), the third is 2 (instead of three) and so forth.

So if we want to make the first NeoPixel at the top left to glow. We will have to address it with 0,0.

## What you achieved @showdialog
You know now how to address a NeoPixel in a matrix, so let's start coding.

## Make the first pixel glow
Drag the block Drag the block **``||neopixelExtended:set matrix color||``** into the editor.

Set the x value (row) to 0 and the y value (column) to 0. Select a color that you like.

Drag the block Drag the block **``||neopixelExtended:show changes||``** into the editor.

See what you have achieved by pressing "Download".

You should now see the NeoPixel glow at the top left corner.

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
strip.setMatrixWiring(neopixelExtended.MatrixDirection.LeftTopToTheRight)
strip.setMatrixWidth(5)
strip.setMatrixHeight(5)
strip.setMatrixColor(0, 0, 0xFFD700)
strip.show()
```

## Finish it yourself
In the picture you can see what we want to achieve. Look at the schematics and try find out which position you have to use for each NeoPixel.

Your code will use the following blocks five times:
* **``||neopixelExtended:set matrix color||``** with the correct position
* **``||neopixelExtended:show changes||``**
* **``||basic:pause||``** with 500ms

~hint Help
If you need help then press the light bulb symbol and you can have a peek at the possible code.
hint~

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, neopixelExtended.Format.RGB)
strip.setMatrixWiring(neopixelExtended.MatrixDirection.LeftTopToTheRight)
strip.setMatrixWidth(5)
strip.setMatrixHeight(5)
strip.setMatrixColor(0, 0, 0xFFD700)
strip.show()
basic.pause(500)
strip.setMatrixColor(1, 1, 0xFFD700)
strip.show()
basic.pause(500)
strip.setMatrixColor(2, 2, 0xFFD700)
strip.show()
basic.pause(500)
strip.setMatrixColor(3, 3, 0xFFD700)
strip.show()
basic.pause(500)
strip.setMatrixColor(4, 4, 0xFFD700)
strip.show()
basic.pause(500)
```