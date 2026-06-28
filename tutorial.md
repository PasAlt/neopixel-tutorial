# NeoPixel Beginner Tutorial

```package
neopixel=github:PasAlt/pxt-neopixel-matrix-extension
```

## Get the necessary equipment

You will need
* 4.5 V battery (e.g. LR12)
* NeoPixel strip with 8 NeoPixels
* 4 cables to connect battery and NeoPixel strip
* Micro:Bit with USB-Cable

Sometimes NeoPixel strips don't have connections that can easily be connected to.  You will have to solder that part on (or ask your teacher to do it).

## Initialize NeoPixel Object

Open the NeoPixel tab on the left side. Then select the first element called **``set strip to..``** and drag it into the **``on start``** block. 

Your NeoPixel is 8 elements long. Therefore, change the number of leds to 8 Neopixels by clicking in it and pressing 8 on your keyboard.

You can leave the rest as it is.

You have now created an object called 'strip' that represents your NeoPixels.

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
```

## Set Colors for the NeoPixels

Drag the block **``setColor``** from the tab NeoPixel below the **``set strip``** block. Choose a color you like by clicking on the color element. 

This part will not let the NeoPixels glow immediately but store what color was set.

See the next step to let the NeoPixels glow.

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
```

## Show 

Open the tab NeoPixel again and drag the element **``show``**  below your current blocks.

Press start to watch your NeoPixels glow in the simulator.

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
strip.show()
```

## Connect NeoPixel strip with Micro:Bit

### Connect both of the ground cable.

The one right beside the "5 VCC" label goes to the battery.
The one right beside the "DIN" label goes to the ground of the Micro:Bit called GND.

## ~ hint

We use black cables for ground

The longer flap of the battery is usually the negative pol which of the battery.

## ~

### Connect power cable then the signal cable

Connect a cable from the battery (+) to the "5 VCC" labelled connection.

Connect a cable from the Micro:Bit to the "DIN" labelled connection. This is our signal that we will use to control the NeoPixels with our Micro:Bit.

![Shows the connected Micro:Bit](/img/connected-micro-bit.png)

## ~ hint

We use red cables from the power source to the device and yellow cables for the signal.

The shorter flap of the battery is usually the positive pol of the battery.

## ~

### Connect your Micro:bit with your computer
Connect your Micro:Bit with your computer, press "Download" and see your NeoPixels glow.

Your NeoPixel do not glow? Check next part for trouble shooting.

## Troubleshooting 

That your NeoPixels are not glowing can have multiple reasons.

Check the following:
* Your battery has enough power: If unsure, use another battery.
* Check that all the cables are correctly and well connected. Trace each connection and compare with the image. Use colors to distinguish the different cables.
* Check your code, especially that you have added **``show``** as last block
* The command to glow is only send at the start. Resend the command by pressing "Download" again 

![Shows the connected Micro:Bit](/img/connected-micro-bit.png)

Still not working? Ask somebody for support (e.g. your teacher).

```blocks
let strip = neopixel.create(DigitalPin.P0, 8, NeoPixelMode.RGB)
strip.setColor(0xff0000)
strip.show()
```