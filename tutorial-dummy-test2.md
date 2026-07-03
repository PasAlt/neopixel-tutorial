# Tutorial NeoPixel matrix

```package
neopixel-extended=github:PasAlt/pxt-neopixel-matrix-extension#v2.0.7
```

## Repeat previous blocks

To change between two immages you will need to add the same blocks **``set Neopixel 5x5``**, **``show``** and **``pause``** again.

Then change the colors in the second ``set Neopixel 5x5`` block that it represents a K.

Run the program by pressing download.

```blocks
let strip = neopixelExtended.create(DigitalPin.P0, 25, NeoPixelMode.RGB)
basic.forever(function () {
    strip.setMatrix25(
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xE60026, 0xFFD700),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xE60026, 0xFFD700),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xFFD700, 0xFFD700)
    )
    strip.show()
    basic.pause(1000)
    strip.setMatrix25(
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xff0000, 0xFFD700),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xFFD700, 0xff0000),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xFFD700, 0xE60026, 0xff0000),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xE60026, 0xFFD700, 0xff0000),
    neopixelExtended.rowOf5(0xff0000, 0xFFD700, 0xff0000, 0xff0000, 0xFFD700)
    )
    strip.show()
    basic.pause(1000)
})
```

